# Asynchronous Programming

Yarn Spinner 3 transitions from the callbacks and coroutines approach of versions 1 and 2 to an asynchronous programming model. This guide explores what this means for your development, how to use these new features, and important considerations when implementing async code.

### What we'll be covering

* Basics of asynchronous programming and `async` and `await` keywords
* Supported awaiters
* Creating your own async code
* How to cancel awaited code
* Using completion sources

### Async Programming

Asynchronous programming isn't drastically different from traditional approaches. In many ways, it's a refinement of the coroutine pattern with some syntax changes and additional capabilities.

At its core, async programming provides a way to write code that performs operations asynchronously. This means your code doesn't block program execution when encountering long-running tasks (such as those spanning multiple frames).

To illustrate this concept, let's use a simple analogy: imagine you are a computer making a cup of tea. Your process might look like this:

1. Fill the kettle
2. Boil the kettle
3. Add tea to the cup
4. Add the water to the cup
5. Add milk to the cup
6. Drink the tea

In non-async code, each step blocks execution - while waiting for the water to boil, you'd be frozen, unable to respond to other inputs or perform other tasks. In async code, these steps remain non-blocking. You can respond to other events while still monitoring the kettle. You'll still wait for the water to boil before proceeding to the next step (you're not performing tasks in parallel), but you won't block the entire system during that wait.

{% hint style="info" %}
While it's tempting to think of async code as parallel processing, they're distinct concepts. Asynchronous programming is about non-blocking execution, not parallel or multithreaded computation.
{% endhint %}

As a developer, you decide which code segments should be async and which should execute synchronously. Ideally, this distinction shouldn't complicate your code's readability or logical flow. That's the essence of async programming.

#### async and await keywords

The primary distinction between asynchronous programming and traditional approaches is the introduction of new keywords. The most significant is `await`, which tells C# to pause execution at that point until the specified asynchronous operation completes, then resume from there.

You can use `await` with any method flagged as asynchronous or any method returning an awaiter (more on these shortly). This brings us to the `async` keyword, which must be added to method signatures that contain awaiting calls. Unity will report errors if you try to `await` code in a method without the `async` keyword, or if you include `async` in a method that doesn't await anything.

These keywords represent the main syntactic differences. While there's considerable complexity enabling asynchronicity under the hood, you rarely need to concern yourself with those details. Simply `await` asynchronous code and add `async`to methods that perform awaiting operations.

This approach brings an additional benefit: it makes asynchronous code easily identifiable. With a quick glance at keywords and method signatures, you can understand which code executes asynchronously and which code awaits other operations, resulting in cleaner, more maintainable code.

#### Async vs Coroutines

You might wonder, "Can't we accomplish all this with coroutines?" It's a valid question. Coroutines have served Unity developers well for years and are widely understood. However, they have several limitations that make async programming a superior alternative in many cases.

First, coroutines cannot return values. While workarounds exist, they're exactly that - workarounds. Async methods can naturally return values without additional complexity.

Second, coroutines lack cancellation context. To stop a coroutine, you need external management code to maintain references and handle cancellation, which becomes increasingly complex with nested coroutines. Moreover, coroutines receive no notification when cancelled, forcing external code to handle cleanup. Async code addresses this through cancellation tokens, which provide cancellation signals allowing code to clean up after itself and propagate cancellation to other async operations it calls. Similarly, exceptions thrown in coroutines can't be caught by the initiating code, whereas async code enables centralized error handling.

Coroutines are also tied to MonoBehaviours. While often convenient, this can force unnecessary Unity dependencies in code that otherwise wouldn't need them, such as networking components.

Additionally, coroutines run on the main thread. This is typically appropriate, but makes offloading work to other threads cumbersome. Async code supports multi-threading more elegantly (though for heavily threaded operations, the Jobs system remains preferable).

Finally, coroutines don't clearly signal their intent in method signatures and call sites. They return `IEnumerator`, giving no indication they represent long-running operations. The difference between `StartCoroutine(MyCoroutine())` and `MyCoroutine()` isn't immediately obvious, and editor-mode coroutines require a completely different approach. Async code uses consistent syntax across all contexts with clear signaling of intent.

While coroutines do work and have some minor advantages, their quirks often lead to more complex, harder-to-maintain code compared to async alternatives.

### Awaiters

The underlying infrastructure for asynchronous programming extends beyond this guide's scope, but different systems provide the necessary components to support awaiting operations. You can think of these as containers for awaited work that can be queried, cancelled, or ignored. Awaiters notify when their work completes, allowing code execution to continue.

{% hint style="info" %}
These constructs have various names across different environments: promises, futures, tasks, and awaitables, among others. We'll use "awaiters" throughout this guide, but you may encounter these other terms elsewhere.
{% endhint %}

Yarn Spinner supports three types of awaiters:

* [Tasks](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.task)
* [Awaitable](https://docs.unity3d.com/6000.0/Documentation/ScriptReference/Awaitable.html)
* [UniTask](https://github.com/Cysharp/UniTask)

We've implemented a system that detects and uses the most appropriate awaiter for your project. We prioritize UniTask if installed, falling back to Awaitables, and finally to Tasks if no other options exist.

{% hint style="info" %}
We recommend using UniTask if possible, as it offers the best balance of features and performance among the three options.
{% endhint %}

This behavior is encapsulated in our `YarnTask` awaiter. `YarnTask` wraps one of the above awaiters and provides conversion methods between different awaiter types, making it easier to use Yarn Spinner with your preferred awaiter system. In most cases, you won't need to think about this - simply using `await` with the appropriate code segments should work seamlessly.

#### Tasks vs Awaitables vs UniTask

While these three awaiter types are similar, each has distinct characteristics worth noting.

Tasks are part of C# rather than Unity, meaning they lack integration with Unity's run loop and GameObject lifecycle. Without careful management, this can lead to unexpected behaviors like GameObject movement after exiting play mode. Tasks also have the highest memory and performance overhead of the three options (though still relatively modest). However, they offer the most extensive API with numerous convenience methods and flexibility - a trade-off for being the most generic option. Tasks are recommended only as a last resort when better alternatives aren't available.

Awaitables are a relatively recent Unity addition. They provide Task-like functionality for common asynchronous Unity operations with awareness of the run loop and GameObject lifecycle. They're more lightweight but less flexible than Tasks. One important caveat: cancelled Awaitables throw exceptions that must be caught - a necessity of their implementation rather than a design flaw, but still a notable difference from Tasks. We recommend Awaitables over Tasks, and most newer Unity versions support them.

UniTask is a third-party asynchronous library that combines the tight engine integration and lightweight footprint of Awaitables with many quality-of-life features from Tasks. Like Awaitables, UniTask throws exceptions when awaited code is cancelled, requiring exception handling. It's our recommended approach for asynchronous programming in Unity.

As mentioned earlier, we've created a `YarnTask` wrapper awaiter. This isn't intended to replace any of the above options, but rather to provide a convenience layer supporting as many developers and Unity versions as possible.

### Making async code

Let's explore creating basic async code by converting a coroutine to an async approach. We'll use a simple example of moving a cube from one position to another over time.

{% hint style="info" %}
In these examples, we use `YarnTask`, but feel free to adapt them to your preferred awaiter type.&#x20;
{% endhint %}

First, here's how you might implement this as a coroutine:

```csharp
IEnumerator MoveCube(float duration, Vector3 goal)
{
    float accumulator = 0;
    Vector3 start = this.transform.position;

    while (accumulator < duration)
    {
        this.transform.position = Vector3.Lerp(start, goal, accumulator / duration);
        yield return null;
        accumulator += Time.deltaTime;
    }
}
```

You would start it like this:

```csharp
void Start()
{
    StartCoroutine(MoveCube(1, new Vector3(10, 0, 0)));
}
```

Now, let's convert this to an async implementation:

```csharp
async YarnTask MoveCube(float duration, Vector3 goal)
{
    float accumulator = 0;
    Vector3 start = this.transform.position;

    while (accumulator < duration)
    {
        this.transform.position = Vector3.Lerp(start, goal, accumulator / duration);
        await YarnTask.Yield();
        accumulator += Time.deltaTime;
    }
}
```

And to start it:

```csharp
async void Start()
{
    await MoveCube(1, new Vector3(10, 0, 0));
}
```

#### Cancellation

Next, let's add cancellation support - after all, what good is a moving cube if its movement can't be stopped?

```csharp
async YarnTask MoveCube(float duration, Vector3 goal, CancellationToken token = default)
{
    float accumulator = 0;
    Vector3 start = this.transform.position;

    while (accumulator < duration && !token.IsCancellationRequested)
    {
        this.transform.position = Vector3.Lerp(start, goal, accumulator / duration);
        await YarnTask.Yield();
        accumulator += Time.deltaTime;
    }
    this.transform.position = goal;
}
```

Now we can clean up when cancelled - in this case, jumping to the end position, though cleanup could mean many different things depending on your implementation.

To use this cancellation feature:

```csharp
async void Start()
{
    await MoveCube(5, new Vector3(10, 0, 0), this.destroyCancellationToken);
}
```

Each MonoBehaviour includes a token that's cancelled when the MonoBehaviour receives the Destroy call. However, this isn't particularly useful here, since we're more interested in cancelling movement before destruction. Let's create a new cancellation token linked to the destroy token that we can cancel independently:

```csharp
CancellationTokenSource cancellationTokenSource;
async void Start()
{
    cancellationTokenSource = CancellationTokenSource.CreateLinkedTokenSource(this.destroyCancellationToken);
    await MoveCube(5, new Vector3(10, 0, 0), cancellationTokenSource.Token);
}
```

Now we have a token we can cancel whenever needed, but because it's linked to the destroy cancellation token, destruction will still cascade cancellation downward. This nesting can be as deep as required, with cancellation propagating through the entire chain with a single call.

We should also handle any exceptions that might be thrown:

```csharp
async void Start()
{
    cancellationTokenSource = CancellationTokenSource.CreateLinkedTokenSource(this.destroyCancellationToken);
    try
    {
        await MoveCube(5, new Vector3(10, 0, 0), cancellationTokenSource.Token);
    }
    catch (System.Exception ex)
    {
        Debug.LogException(ex);
    }
}
```

To test cancellation, we can trigger it in response to user input:

```csharp
void Update()
{
    // if you release tab the cube movement is cancelled
    if (Input.GetKeyUp(KeyCode.Tab))
    {
        cancellationTokenSource.Cancel();
    }
}
```

You can safely call cancel multiple times without negative consequences, as the tokens handle this gracefully. With that, we've created a fully async and cancellable cube movement system!

#### Returning Values

Moving cubes is useful, but we're still performing tasks without communication. Let's return a value from our async method. Imagine creating a custom dialogue option selector that rolls a die and selects the option corresponding to the result:

```csharp
async YarnTask<int> RollDice(int totalNumberOfOptions, CancellationToken cancellationToken)
{
    // animate in the dice
    await FadeUpDiceAnimation(token);
    // generate a random number
    int number = UnityEngine.Random(0, count);
    // animate the dice rolling to that number
    await AnimateRoll(number, token);
    // animate away the dice
    await FadeDownDiceAnimation(token);
    // returning the value
    return number;
}
```

Then in our `RunOptionsAsync` method, we await the roll and use the result to select an option:

```csharp
public override async YarnTask<DialogueOption> RunOptionsAsync(DialogueOption[] dialogueOptions, CancellationToken cancellationToken)
{
    int roll = await RollDice(dialogueOptions.Count, cancellationToken);

    return dialogueOptions[roll];
}
```

Notice we're using a generic form of `YarnTask`, where the generic type specifies the return type: `YarnTask<int>` for the dice roller and `YarnTask<DialogueOption>` for the dialogue option selection. We don't need to explicitly return a `YarnTask<T>` (though we can) - C# is smart enough to infer the appropriate return type.

#### Completion Sources

The final major async component is completion sources. These are particularly useful for converting non-asynchronous code, especially UI with callbacks like buttons, to work with async patterns.

A completion source allows external objects to set a completion result, which other code can await like any other async task. For example:

```csharp
public class ButtonWaiter : MonoBehaviour
{
    public YarnTaskCompletionSource buttonCompletion;
    public Button button;
    async void Start()
    {
        button.onClick.AddListener(() =>
        {
            buttonCompletion.TrySetResult();
        });
    }
}
```

In your custom presenter code, you might use this like:

```csharp
public override async YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
{
    // configuring 
    var completionSource = new YarnTaskCompletionSource();
    buttonWaiter.buttonCompletion = completionSource;
    
    // fade in the UI, including our button
    await FadeInUI();

    // start waiting on the button
    await buttonWaiter.Task;

    // fade down the UI
    await FadeOutUI();
}
```

Now the line will wait for the user to press the button before continuing.

Completion sources can also return values. This is how the default options presenter works - each option item receives the same completion source, and when selected, it sets the completion source with the chosen option:

```csharp
OnOptionSelected.TrySetResult(this.Option);
```

The selected value is then returned to the dialogue system:

```csharp
// Wait for a selection to be made, or for the task to be completed.
var completedTask = await selectedOptionCompletionSource.Task;

// finally we return the selected option
return completedTask;
```

### Conclusion

You now have a foundational understanding of async programming and how it's implemented in Yarn Spinner. This knowledge is essential for creating custom dialogue presenters and other interactive components in your Yarn Spinner projects.

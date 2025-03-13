# Try Yarn Spinner

## Writing Yarn with Try Yarn Spinner

When you first start learning Yarn, you can use [**Try Yarn Spinner**](https://try.yarnspinner.dev/), our introductory, browser- based tool for writing Yarn Spinner Scripts. No installation necessary!

{% hint style="info" %}
As you learn to write dialogue and game scripts with Yarn, you'll eventually need to use our editor, which is a Visual Studio Code Extension. Before you get to that stage, the best place to experiment with, and explore Yarn Spinner, is [Try Yarn Spinner](https://try.yarnspinner.dev).
{% endhint %}

{% stepper %}
{% step %}
#### Open your web browser, and navigate to **Try Yarn Spinner** at [https://try.yarnspinner.dev](https://try.yarnspinner.dev/)

In **Yarn**, everything you write is text and structured around **nodes** and **lines**.

In **Try Yarn Spinner**, the first node to run is always called **Start**, so we’ll write that now.

{% hint style="info" %}
In your own games or narratives outside of Try Yarn Spinner, the first node can be named whatever you like.
{% endhint %}
{% endstep %}

{% step %}
**Copy and paste, or write, this Yarn Spinner script into Try Yarn Spinner, and hit the Run button in the top-right.**&#x20;

<pre class="language-markup" data-line-numbers><code class="lang-markup"><a data-footnote-ref href="#user-content-fn-1">title: Start</a>
<a data-footnote-ref href="#user-content-fn-2">---</a>
<a data-footnote-ref href="#user-content-fn-3">Narrator:</a> Hi, I'm the narrator for the documentation!
<a data-footnote-ref href="#user-content-fn-4">===</a>
</code></pre>
{% endstep %}

{% step %}
**Check out the playable version of this Yarn Spinner script on the right-side of the screen.**

<figure><img src="../.gitbook/assets/Screenshot 2025-03-07 at 1.22.45 pm.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

### What did we just do?

We just wrote a simple Yarn Spinner script consisting of one **node** (titled `Start`), with one **line** inside that node, delivering a greeting from a narrator.

The title of your nodes is important, because your game uses node titles to tell Yarn Spinner which node to start running. You also use the title of a node when you want to jump to another node, as you'll see soon.

{% hint style="info" %}
Node titles are never shown to the player and must start with a letter, and can contain any letters, numbers and underscores (but cannot contain a period or other symbols)
{% endhint %}

[^1]: This is called a **header**. This **header** is the **title**, and it’s always required in each node.

[^2]: This indicates the start of a node's content.

[^3]: This is a character name. Character names in Yarn Spinner are optional. If they exist, they're always at the beginning of a line, and consist of any text, followed by a colon.

[^4]: This indicates the end of a node.

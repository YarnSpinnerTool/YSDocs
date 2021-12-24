---
description: Upgrading your Yarn Spinner 1.x scripts to Yarn Spinner 2.x is easy.
---

# 🪄 Upgrading older Yarn

The Yarn Spinner Console (`ysc`) can upgrade your older `.yarn` scripts to the latest syntax.&#x20;

{% hint style="info" %}
The Yarn Spinner Console (`ysc`) is in heavy development, and is likely to have its own complete section here, in the documentation, before long. Until then, find further initial documentation via [its GitHub project](https://github.com/YarnSpinnerTool/YarnSpinner-Console).
{% endhint %}

To upgrade your scripts:

**Install the version of Yarn Spinner Console that matches your version of Yarn Spinner**. You can do this via the [Yarn Spinner Console GitHub Project](https://github.com/YarnSpinnerTool/YarnSpinner-Console). Choose _Releases_ in the sidebar, and download the appropriate binary for your platform. If you just want the latest release, you can find it [here](https://github.com/YarnSpinnerTool/YarnSpinner-Console/releases/latest).

**Run the upgrader on your scripts.** To upgrade, you must run `ysc` on your command-line/terminal with the `upgrade` parameter and a path to a `yarn file:`

```
$ ysc upgrade myOldYarnFile.yarn
```

You can also run the upgrade on multiple scripts at once. To do this, you can pass in as many `.yarn` files as you want:

```
ysc upgrade myOldYarnFile.yarn myOtherOldYarnFile.yarn
```

---
title: "Typora - Markdown Editor"
date: 2021-12-31 16:20
comments: true
related: true
categories: productivity
tags: 
  - "#typora"
  - "#markdown"
  - "#mermaid"
  - "#jekyll"
teaser: A Well Designed Markdown Editor for Writing
---

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
<script>
 mermaid.initialize({ startOnLoad: true });
</script>


While catching up on my reading, I came across a reference (and praise) for [Typora](https://typora.io), a new markdown editor, that had recently come out of a long beta cycle.  I do a lot of composing in markdown (usually in VSCode) and use Marked 2 for preview and publishing.

Typora's website provides an excellent introduction to the tool.  Typora allows you to type markdown and quickly see the impact of any markup when you aren't editing that section of the text.  I also noted that my [Grammarly Desktop app](https://www.grammarly.com/desktop) provides its services in the composition process.

Typora allows one to have the front-matter at the top of the file required by MultiMarkdown and Jekyll.  It also incorporates source code highlighting, showing linked images, $$\LaTeX$$-style math equations such as

$$\tan(x) = \frac{\sin(x)}{\cos(x)},$$

and [Mermaid drawings](https://mermaid-js.github.io/mermaid/#/) such as

<div class="mermaid">
sequenceDiagram
    title: User deposits $100 into checking account
    actor User
    participant CheckingAccount
    note right of CheckingAccount:  increases balance from <br/>$1000 to $1100 which is logged 
    participant TLogger
    User->>CheckingAccount: deposit(10000)
    activate CheckingAccount
    CheckingAccount->>TLogger: logTransaction(name,'deposit',10000,110000)
    activate TLogger
    deactivate TLogger
    deactivate CheckingAccount
</div>

To use the generated markdown in Jekyll to embed $$\LaTeX$$, one must include the non-code block text

```html
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>
```

somewhere, while using Mermaid will require including the non-code block text

```html
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
<script>
 mermaid.initialize({ startOnLoad: true });
</script>
```

and changing the Jekyll-bound markdown to remove the Mermaid code block and wrap the code with use `<div class="mermaid">...</div>`

Typora has a 15-day trial and costs $15 (one-time) for continued use.  Typora is licensed per user and allows use on three devices.  The site also notes that versions are available for macOS, Linux, and Windows.


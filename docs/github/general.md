---
title: Markdown for GitHub
description: All the Markdown features available on GitHub.
hide:
- navigation
- toc
---

# :octicons-markdown-16: General
This page lists all features that can be used across all places on GitHub, which support markdown formatting.

--8<-- "toc.txt"

----
## Headers
Headers are larger text like shown above and also allow you to link to it, when used in Markdown files or the Wiki.

//// example
/// tab | Markdown
```markdown
# H1 Header
## H2 Header
### H3 Header
#### H4 Header
##### H5 Header
###### H6 Header

----
Alternative Headers

Alt H1 Header
===

Alt H2 Header
---
```
///

/// tab | Result
<!-- HTML headers are used to prevent MkDocs from embedding them -->

<h1>H1 Header</h1>
<h2>H2 Header</h2>
<h3>H3 Header</h3>
<h4>H4 Header</h4>
<h5>H5 Header</h5>
<h6>H6 Header</h6>

----
Alternative Headers

<h1>Alt H1 Header</h1>

<h2>Alt H2 Header</h2>
///
////

----
## Text formatting
GitHub offers normal Markdown formatting but also adds some own styling.

### Italic
You can display a text in italic by surrounding it either with a single asterisks (`*`) or underscore (`_`).

//// example
/// tab | Markdown
```markdown
You can use *asterisks* to make text *italic*.

Alternatively can you also use _underscores_.
```
///

/// tab | Result
You can use *asterisks* to make text *italic*.

Alternatively can you also use _underscores_.
///
////

### Bold
Using two Asterisks (`*`) or two underscores (`_`) before and after the text makes it bold.

//// example
/// tab | Markdown
```markdown
You can use **two asterisks** to make text **bold**.

Alternatively can you also use __two underscores__.
```
///

/// tab | Result
You can use **two asterisks** to make text **bold**.

Alternatively can you also use __two underscores__.
///
////

### Strikethrough
This is a GitHub exclusive formatting code, where you use two tilde (`~`) before and after text to make it strikethrough.

//// example
/// tab | Markdown
```markdown
Don't like this text? Just ~~cross it out!~~
```
///

/// tab | Result
Don't like this text? Just ~~cross it out!~~
///
////

### Combinations
You can combine the above [formatting options](#text-formatting) to have more special text.

//// example
/// tab | Markdown
```markdown
<!-- Note: You have to use underscores when already using asterisks -->
Here is some *italic text with __additional bold__*

Or how about ~~strikethrough with *italic?*~~
```
///

/// tab | Result
Here is some *italic text with __additional bold__*

Or how about ~~strikethrough with *italic*?~~
///
////

### Quotes
Starting a line with a `>` followed by a space makes it possible for you to *quote* a message.  
The message will have a little bar on the left side and slightly different styling. All types of markdown formatting are supported including quotes in quotes!

Note that you need an empty line between a quote and any normal text below it to not include it in the quote.

//// example
/// tab | Markdown
```markdown
Albert Einstein once said:  
> Once you stop learning you start dying.
```
///

/// tab | Result
Albert Einstein once said:  
> Once you stop learning you start dying.
///
////

#### Special Quote blocks

/// extensions | MkDocs Extensions used
    attrs: {class: 'inline end'}

[PyMdownx's Blocks.Admonition][blocks-admonition]{ target="_blank" rel="nofollow" }  
(Custom CSS for styling)
///

GitHub implemented a feature where a Quote block starting with `[!NOTE]`, `[!TIP]`, `[!IMPORTANT]`, `[!WARNING]` or `[!CAUTION]` will be rendered as a callout block.  
This callout block will have a border on the left like a quote, but also some smaller differences to it:

- Border will be colored based on the type of callout
- First line (The `[!...]`) will be colored the same as the border and prefixed with an icon.
- Any displayed text in it will use the default text color used for rendered markdown files.

/// warning | Important!
- The first line needs to be `> ` followed by `[!NOTE]`, `[!TIP]`, `[!IMPORTANT]`, `[!WARNING]` or `[!CAUTION]`
- This feature is still in beta and may have bugs or not work across all GitHub.
///

[blocks-admonition]: https://facelessuser.github.io/pymdown-extensions/extensions/blocks/plugins/admonition/

///// example
//// tab | Markdown
```markdown
> [!NOTE]
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Crucial information necessary for users to succeed.

> [!WARNING]
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.
```
////

//// tab | Result
/// gh-note | Note
    attrs: {class: 'gh-admonition'}

Highlights information that users should take into account, even when skimming.
///

/// gh-tip | Tip
    attrs: {class: 'gh-admonition'}

Optional information to help a user be more successful.
///

/// gh-important | Important
    attrs: {class: 'gh-admonition'}

Crucial information necessary for users to succeed.
///

/// gh-warning | Warning
    attrs: {class: 'gh-admonition'}

Critical content demanding immediate user attention due to potential risks.
///

/// gh-caution | Caution
    attrs: {class: 'gh-admonition'}

Negative potential consequences of an action.
///
////
/////

### Horizontal rule
Using three or more hyphens (`-`), astersisks (`*`) or underscores (`_`) will create a horizontal rule (line) which goes accross the entire text area.

//// example
/// tab | Markdown
```markdown
Use three or more hyphens, asterisks or underscores to make a line

---
But make sure there is no text directly above them or it will be converted to a H2 header!
```
///

/// tab | Result
Use three or more hyphens, asterisks or underscores to make a line

---
But make sure there is no text directly above them or it will be converted to a H2 header!
///
////

### Line breaks
To indicate a line break, end a line with two spaces (indicated below using `◦`), a backslash (`\`) or a `<br>` html tag.

/// note
Issues and Pull requests don't require two spaces at the end for line breaks.
///

//// example
/// tab | Markdown
```markdown
We make line breaks, by ending a line with two spaces.◦◦
This line will show below the other.

For a new paragraph, leave an empty line in between.
```
///

/// tab | Result
We make line breaks, by ending a line with two spaces.  
This line will show below the other.

For a new paragraph, leave an empty line in between.
///
////

### Footnotes

/// extensions | MkDocs Extensions used
    attrs: {class: 'inline end'}

[Python Markdown's Footnotes extension][footnotes-extension]{ target="_blank" rel="nofollow" }
///

[footnotes-extension]: https://python-markdown.github.io/extensions/footnotes/

The footnote syntax allows you to link text or URLs without destroying the text's look and formatting.  
To use a footnote, simply use `[^n]` - where `n` is a number or text to use - in the place you want a footnote to be placed and use `[^n]: <text>` to make a link.

The `[^n]: <text>` part can be anywhere in your markdown file.

When generated will the footnotes always appear at the bottom of the page. They will also contain a link that goes back to the footnote's locations. Multiple `[^n]` can exist to link to the same repherence.

//// example
/// tab | Markdown
```markdown
Markdown[^1] is a lightweight markup language[^markup] used for creating formatted text.  
It also allows usage of HTML[^html] in it.

[^1]: https://daringfireball.net/projects/markdown/syntax
[^markup]: In computer text processing, a markup language is a system for annotating a document in a way that is visually distinguishable from the content.
  Source: https://en.wikipedia.org/wiki/Markup_language

<!-- This is a different syntax you can use for multi-line text -->
[^html]:
    Hypertext Markup Language.  
    Made by the World Wide Web Consortium (W3C).
```
///

/// tab | Result
Markdown[^1] is a lightweight markup language[^markup] used for creating formatted text.  
It also allows usage of HTML[^html] in it.
        
[^1]: https://daringfireball.net/projects/markdown/syntax  
[^markup]: In computer text processing, a markup language is a system for annotating a document in a way that is visually distinguishable from the content.  
    Source: https://en.wikipedia.org/wiki/Markup_language  
[^html]:
    Hypertext Markup Language.  
    Made by the World Wide Web Consortium (W3C).
///
////

----
## Lists
You can have various types of lists to order things.

### Ordered
Starting a line with any number followed by a dot, space and text makes a new Ordered list.

//// example
/// tab | Markdown
```markdown
1. This is the first entry.
2. This is the second one.
4. The numbers don't even have to make sense!

----

1. To indent an entry...
   1. ...add 3 spaces before it.
```
///

/// tab | Result
1. This is the first entry.
2. This is the second one.
4. The numbers don't even have to make sense!

----

1. To indent an entry...
    1. ...add 4 spaces before it.
///
////

### Unordered
The unordered list has the same behaviour as the ordered list, with the difference that it doesn't use a number and dot, but instead either an asterisk (`*`) or a hyphen/dash (`-`)

//// example
/// tab | Markdown
```markdown
- This list
- doesn't use numbers.

----

* Because it is
* unordered.

----

- Unordered lists...
    - ...also use 4 spaces for indents.
```
///

/// tab | Result
- This list
- doesn't use numbers.

----

* Because it is
* unordered.

----

- Unordered lists...
    - ...also use 4 spaces for indents.
///
////

### Task Lists

/// extensions | MkDocs Extensions used
    attrs: {class: 'inline end'}

[PyMdownx's tasklist extension][tasklist-extension]{ target="_blank" rel="nofollow" }
///

[tasklist-extension]: https://facelessuser.github.io/pymdown-extensions/extensions/tasklist/

Adding a `[ ]` after a hyphon or asterisks followed by text will create a task list item.  
This task list item is "unchecked" (Shows an empty box) but can be "checked" by using `[x]` instead.

Another unique feature is that a task-list item containing an issue, Pull request or Discussion ID (`#:id`) will link to it and also display the status of said issue/PR/discussion.  
Refer to the [`Issues, Pull requests and Discussions` page](issues-pull-requests-and-discussions.md) for more info.

//// example
/// tab | Markdown
```markdown
- [x] Buy milk
- [x] Make laundry
- [ ] Take over the world
```
///

/// tab | Result
- [x] Buy milk
- [x] Make laundry
- [ ] Take over the world
///
////

#### Unique behaviour of Task Lists
Task lists may show the issues icon (:octicons-issue-opened-16:) on the right-hand side if hovered over and when used in an issue or Pull request.  
Clicking this icon will allow to open a new issue that links to this entry.

### Note about mixed lists
You can mix the different list types, but keep in mind that you will need to use 3 or 4 spaces to indent a List of a different type.

----
## Links

/// extensions | MkDocs Extensions used
    attrs: {class: 'inline end'}

[PyMdownx's magiclink extension][magiclink-extension]
///

[magiclink-extension]: https://facelessuser.github.io/pymdown-extensions/extensions/magiclink/

You can link to stuff in various ways

### Normal
Linking to a page normally is simple. Either post the link directly, or use `[text](link)`

//// example
/// tab | Markdown
```markdown
You can link to sites by posting the URL: https://github.com

Or you link to it as an [embedded link](https://github.com).  
You can even give it [a title](https://github.com 'Go to GitHub!') to show on hover!
```
///

/// tab | Result
You can link to sites by posting the URL: https://github.com

Or you link to it as an [embedded link](https://github.com).  
You can even give it [a title](https://github.com 'Go to GitHub!') to show on hover!
///
////

### Reference
Reference URLs are similar to normal ones, with the difference, that you only enclose the text in square brackets and it becomes a embedded link (when text matches).  
You can use the same reference link at multiple places and use `[text][reference link text]` in case the text would be different than the reference link's text.

/// info | Names used in reference links are case-insensitive.
///

//// example
/// tab | Markdown
```markdown
[link]: https://google.com
[GitHub]: https://github.com

[Reference links][link] can be used like that to link to sites like [GitHub]!
```
///

/// tab | Result
[Reference links][link] can be used like that to link to sites like [GitHub]!
///
////

[link]: https://google.com
[GitHub]: https://github.com

### Image
Images can be added the same way as links (including reference link-style), but have an exclamation mark (`!`) before them.

//// example
/// tab | Markdown
```markdown
[github_logo]: https://docs.andre601.ch/GitHub-Markdown/assets/img/github.png

![name][github_logo]  
![github_text](https://docs.andre601.ch/GitHub-Markdown/assets/img/github-text.png)
```
///

/// tab | Result
![name][github_logo]  
![github_text](https://docs.andre601.ch/GitHub-Markdown/assets/img/github-text.png)
///
////

[github_logo]: https://docs.andre601.ch/GitHub-Markdown/assets/img/github.png

----
## Code
GitHub supports inline code and code blocks with syntax highlighting.

### Inline code
To make inline code, surround the the text with a single backtick (`` ` ``).  

/// tip
To display backticks within inline code, start and end it using **2 backticks**.
///

//// example
/// tab | Markdown
```markdown
This is text with some `inline code`.
```
///

/// tab | Result
This is text with some `inline code`.
///
////

### Code Block
Code blocks allow to display multi-line code and even have [syntax highlighting](#syntax-highlighting).  
To put text into a code block, surround it with three backticks (```` ``` ````).

/// tip
To display three backticks inside a code block, start and end one with **4 backticks**.
///

//// example
/// tab | Markdown
````markdown
This is some code block stuff
```
hello world!
```
````
///

/// tab | Result
This is some code block stuff
```
hello world!
```
///
////

#### Syntax highlighting
GitHub provides `syntax highlighting` support which means that the content within a codeblock can be colorized, depending on what coding language was selected.

/// note
GitHub supports displaying of Diagrams, Flowcharts, etc. through Mermaid.js.  
To display such a graph, use `mermaid` as the syntax highlighting and provide a Mermaid-compatible format to turn into a graph.
///

//// example
/// tab | Markdown
````markdown
This here is some JSON with syntax highlighting:
```json
{
    "hello": "world!",
    "how": [
        "are",
        "you?"
    ]
}
```
````
///

/// tab | Result
This here is some JSON with syntax highlighting:
```json
{
    "hello": "world!",
    "how": [
        "are",
        "you?"
    ]
}
```
///
////

----
## Tables
Making tables in Markdown is fairly simple.

//// example
/// tab | Markdown
```markdown
| Example      | One             |
|--------------|-----------------|
| You can make | it look pretty! |

Example | Two
---|---
Not so pretty... | Yet it still works.

----
Text alignment

| Title 1 | Title 2 | Title 3 | Title 4 |
|---------|:--------|:-------:|--------:|
| Default | Left    | Center  | Right   |
```
///

/// tab | Result
| Example      | One             |
|--------------|-----------------|
| You can make | it look pretty! |

Example | Two
---|---
Not so pretty... | Yet it still works.

----
Text alignment

| Title 1 | Title 2 | Title 3 | Title 4 |
|---------|:--------|:-------:|--------:|
| Default | Left    | Center  | Right   |
///
////

----
## Emojis

/// extensions | MkDocs Extensions used
    attrs: {class: 'inline end'}

[PyMdownx's Emoji Extension][emoji-extension]{ target="_blank" rel="nofollow" }
///

[emoji-extension]: https://facelessuser.github.io/pymdown-extensions/extensions/emoji/

GitHub allows to render emojis.  
A emoji is defined using a starting colon (`:`) followed by any alphanummerical text, hyphens (`-`) and underscores (`_`) amd ends with anothor colon.

All available Emojis can be found on @ikatyang/emoji-cheat-sheet

Note that the emojis displayed may look different depending on the Operating System you use. This site uses Twemojis for consistent emoji display.

//// example
/// tab | Markdown
```markdown
Valid Emoji:
:smile:

Invalid Emoji:
:some emoji:
```
///

/// tab | Result
Valid Emoji:  
:smile:

Invalid Emoji:  
Some Emoji
///
////

----
## Math expressions

/// extensions | MkDocs Extensions Used
    attrs: {class: 'inline end'}

[PyMdownx's Arithmatex Extension][arithmatex-extension]{ target="_blank" rel="nofollow" }
///

[arithmatex-extension]: https://facelessuser.github.io/pymdown-extensions/extensions/arithmatex/

GitHub supports the LaTeX format to display complex math expressions using normal text.  

To display a math expression, start and end the line(s) with dollar symbols (`$`).  
One dollar symbol at the start and end is used to indicate an inline math expression, while two dollar symbols at the start and end indicate a block.

/// tip | Alternative syntaxes
There are other syntaxes that can be used to indicate the start and end of a math expression, namely:

- ``$`...`$`` for inline.
- Using `math` as syntax highlighting in code blocks.
///

//// example
/// tab | Markdown
```markdown
Inline math: $\sqrt{3x-1}+(1+x)^2$

Cauchy-Schwarz Inequality:

$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$
```
///

/// tab | Result
Inline math: $\sqrt{3x-1}+(1+x)^2$

Cauchy-Schwarz Inequality:

$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$
///
////

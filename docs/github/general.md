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

!!! example
    === "Markdown"
        ```markdown
        # H1 Header
        ## H2 Header
        ### H3 Header
        #### H4 Header
        ##### H5 Header
        ###### H6 Header
        
        ----
        Alternative Headers (H1 and H2 only)
        
        Alt H1 Header
        ======
        
        Alt H2 Header
        ------
        ```
        
    === "Result"
        <!-- We use html tags to avoid the ToC generator from including them -->
        
        <h1>H1 Header</h1>
        <h2>H2 Header</h2>
        <h3>H3 Header</h3>
        <h4>H4 Header</h4>
        <h5>H5 Header</h5>
        <h6>H6 Header</h6>
        
        ----
        Alternative Headers (H1 and H2 only)
        
        <h1>Alt H1 Header</h1>
        
        <h2>Alt H2 Header</h2>

----
## Text formatting
GitHub offers normal Markdown formatting but also adds some own styling.

### Italic
You can display a text in italic by surrounding it either with a single asterisks (`*`) or underscore (`_`).

!!! example
    === "Markdown"
        ```markdown
        You can use *asterisks* to make text *italic*.
        
        Alternatively can you also use _underscores_.
        ```
        
    === "Result"
        You can use *asterisks* to make text *italic*.
        
        Alternatively can you also use _underscores_

### Bold
Using two Asterisks (`*`) or two underscores (`_`) before and after the text makes it bold.

!!! example
    === "Markdown"
        ```markdown
        You can use **two asterisks** to make text **bold**.
        
        Alternatively can you also use __two underscores__.
        ```
        
    === "Result"
        You can use **two asterisks** to make text **bold**.
        
        Alternatively can you also use __two underscores__.

### Strikethrough
This is a GitHub exclusive formatting code, where you use two tilde (`~`) before and after text to make it strikethrough.

!!! example
    === "Markdown"
        ```markdown
        Don't like this text? Just ~~cross it out!~~
        ```
        
    === "Result"
        Don't like this text? Just ~~cross it out!~~

### Combinations
You can combine the above [formatting options](#text-formatting) to have more special text.

!!! example
    === "Markdown"
        ```markdown
        <!-- Note that you have to use underscores when already using asterisks -->
        Here is some *italic text with __additional bold__*
        
        Or how about ~~strikethrough with *italic*?~~
        ```
        
    === "Result"
        Here is some *italic text with __additional bold__*
        
        Or how about ~~strikethrough with *italic*?~~

### Quotes
Starting a line with a `>` followed by a space makes it possible for you to *quote* a message.  
The message will have a little bar on the left side and slightly different styling. All types of markdown formatting are supported including quotes in quotes!

Note that you need an empty line between a quote and any normal text below it to not include it in the quote.

!!! example
    === "Markdown"
        ```markdown
        Albert Einstein once said:  
        > Once you stop learning you start dying.
        ```
        
    === "Result"
        Albert Einstein once said:  
        > Once you stop learning you start dying.

#### Special Quote blocks
GitHub added a feature where if a quote block starts with either `[!NOTE]`, `[!WARNING]` or `[!IMPORTANT]`, it will be rendered differently.  
In addition will the rendered block be a `div` and not a `quoteblock`, while the text will also be default white

!!! warning "Important!"
    
    - The first line needs to be `> ` followed by `[!NOTE]`, `[!WARNING]` or `[!IMPORTANT]`. Any text to display needs to be on a new line using the quote-pattern.
    - This feature is currently not available in [the wiki](wiki.md).

!!! extensions "MkDocs Extensions"
    - [Python Markdown's Admonition][admonition-extension]{ target="_blank" rel="nofollow" } (Uses custom CSS)

[admonition-extension]: https://python-markdown.github.io/extensions/admonition/

!!! example
    === "Markdown"
        ```markdown
        >  [!NOTE]\
        > Drink water to stay hydrated!
        
        ----
        
        > [!WARNING]\
        > Not drinking water regularely is unhealthy!

        ----

        > [!IMPORTANT]\
        > Dirty water is not healthy either.
        ```
    
    === "Result"
        !!! gh-note "Note"
            Drink water to stay hydrated!
        
        ----
        
        !!! gh-warning "Warning"
            Not drinking water regularely is unhealthy!
        
        ----
        
        !!! gh-important "Important"
            Dirty water is not healthy either.

### Horizontal rule
Using three or more hyphens (`-`), astersisks (`*`) or underscores (`_`) will create a horizontal rule (line) which goes accross the entire text area.

!!! example
    === "Markdown"
        ```markdown
        Use three or more hyphens, asterisks or underscores to make a line
        
        ---
        But make sure there is no text directly above them or it will be converted to a H2 Header!
        ```
        
    === "Result"
        Use three or more hyphens, asterisks or underscores to make a line
        
        ---
        But make sure there is no text directly above them or it will be converted to a H2 Header!

### Line breaks
To indicate a line break, end a line with two spaces (indicated below using `◦`), a backslash (`\`) or a `<br>` html tag.

!!! note
    Issues and Pull requests don't require two spaces at the end for line breaks.

!!! example
    === "Markdown"
        ```markdown
        We make line breaks, by ending a line with two spaces.◦◦
        This line will show below the other.
        
        For a new paragraph, leave an empty line in between.
        ```
        
    === "Result"
        We make line breaks, by ending a line with two spaces.  
        This line will show below the other.
        
        For a new paragraph, leave an empty line in between.

### Footnotes
The footnote syntax allows you to link text or URLs without destroying the text's look and formatting.  
To use a footnote, simply use `[^n]` - where `n` is a number or text to use - in the place you want a footnote to be placed and use `[^n]: <text>` to make a link.

The generated footnotes will link to each other.

!!! extensions "MkDocs Extensions"
    - [Python Markdown's Footnotes extension][footnotes-extension]{ target="_blank" rel="nofollow" }

[footnotes-extension]: https://python-markdown.github.io/extensions/footnotes/

!!! example
    === "Markdown"
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
        
    === "Result"
        Markdown[^1] is a lightweight markup language[^markup] used for creating formatted text.  
        It also allows usage of HTML[^html] in it.
        
[^1]: https://daringfireball.net/projects/markdown/syntax  
[^markup]: In computer text processing, a markup language is a system for annotating a document in a way that is visually distinguishable from the content.  
    Source: https://en.wikipedia.org/wiki/Markup_language  
[^html]:
    Hypertext Markup Language.  
    Made by the World Wide Web Consortium (W3C).
        
----
## Lists
You can have various types of lists to order things.

### Ordered
Starting a line with any number followed by a dot, space and text makes a new Ordered list.

!!! example
    === "Markdown"
        ```markdown
        1. This is the first entry.
        2. This is the second one.
        4. The numbers don't even have to make sense!
        
        ----
        
        1. To indent an entry...
           1. ...add 3 spaces before it.
        ```
        
    === "Result"
        1. This is the first entry.
        2. This is the second one.
        4. The numbers don't even have to make sense!
        
        ----
        
        1. To indent an entry...
            1. ...add 3 spaces before it.

### Unordered
The unordered list has the same behaviour as the ordered list, with the difference that it doesn't use a number and dot, but instead either an asterisks (`*`) or a hyphen/dash (`-`)

!!! example
    === "Markdown"
        ```markdown
        - This list
        - doesn't use numbers.
        
        ----
        
        * Because it is
        * unordered.
        
        ----
        
        - Unordered Lists...
          - ...only require 2 spaces for an indent.
        ```
        
    === "Result"
        - This list
        - doesn't use numbers.
        
        ----
        
        * Because it is
        * unordered.
        
        ----
        
        - Unordered Lists...
            - ...only require 2 spaces for an indent.

### Task Lists
Adding a `[ ]` after a hyphon or asterisks followed by text will create a task list item.  
This task list item is "unchecked" (Shows an empty box) but can be "checked" by using `[x]` instead.

!!! extensions "MkDocs Extensions"
    - [PyMdownX's tasklist extension][tasklist-extension]{ target="_blank" rel="nofollow" } (Uses custom CSS)

[tasklist-extension]: https://facelessuser.github.io/pymdown-extensions/extensions/tasklist/

!!! example
    === "Markdown"
        ```markdown
        Things to do:
        
        - [x] Buy milk
        - [x] Make laundry
        - [ ] Take over the world
        ```
        
    === "Result"
        Things to do:
        
        - [x] Buy milk
        - [x] Make laundry
        - [ ] Take over the world

#### Unique behaviour of Task Lists
Task lists may show the issues icon (:octicons-issue-opened-16:) on the right-hand side if hovered over and when used in an issue or Pull request.  
Clicking this icon will allow to open a new issue that links to this entry.

#### Note about mixed lists
You can mix the different list types, but keep in mind that you will need to use 3 or 4 spaces to indent a List of a different type.

----
## Links
You can link to stuff in various ways

### Normal
Linking to a page normally is simple. Either post the link directly, or use `[text](link)`

!!! example
    === "Markdown"
        ```markdown
        You can link to sites by posting the URL: https://github.com
        
        Or you link to it as an [embedded link](https://github.com).  
        You can even give it [a title](https://github.com 'Go to GitHub!') to show on Hover!
        ```
        
    === "Result"
        You can link to sites by posting the URL: https://github.com
        
        Or you link to it as an [embedded link](https://github.com).  
        You can even give it [a title](https://github.com 'Go to GitHub!') to show on Hover!

### Reference
Reference URLs are similar to normal ones, with the difference, that you only enclose the text in square brackets and it becomes a embedded link (when text matches).  
You can use the same reference link at multiple places and use `[text][reference link text]` in case the text would be different than the reference link's text.

!!! example
    === "Markdown"
        ```markdown
        [Link]: https://google.com
        [GitHub]: https://github.com
        
        [Reference links][Link] can be used like that to link to sites like [GitHub]!
        ```
        
    === "Result"
        [Reference links][Link] can be used like that to link to sites like [GitHub]!

[Link]: https://google.com
[GitHub]: https://github.com

### Image
Images can be added the same way as links (including reference link-style), but have an exclamation mark (`!`) before them.

!!! example
    === "Markdown"
        ```markdown
        [github_logo]: https://andre601.ch/GitHub-Markdown/assets/img/github.png
        
        ![name][github_logo]  
        ![github_text](https://andre601.ch/GitHub-Markdown/assets/img/github-text.png)
        ```
        
    === "Result"
        ![name][github_logo]
        
        ![github_text](https://andre601.ch/GitHub-Markdown/assets/img/github-text.png)

[github_logo]: https://andre601.ch/GitHub-Markdown/assets/img/github.png

----
## Code
GitHub supports inline code and code blocks with syntax highlighting.

### Inline code
To make inline code, surround the the text with a single backtick (`` ` ``).  

!!! tip "Pro-tip"
    If you want to display backticks within inline code will you need to start and end the text with **2 backticks**.

!!! example
    === "Markdown"
        ```markdown
        This is text with some `inline code`.
        ```
        
    === "Result"
        This is text with some `inline code`.

### Code Block
Code blocks allow to display multi-line code and even have [syntax highlighting](#syntax-highlighting).  
To put text into a code block, surround it with three backticks (```` ``` ````).

!!! tip "Pro-tip"
    If you want to display three backticks within code blocks will you need to start and end the text with **4 backticks**.

!!! example
    === "Markdown"
        ````markdown
        This is some code block stuff  
        ```
        hello world
        ```
        ````
        
    === "Result"
        This is some code block stuff  
        ```
        hello world
        ```

<!-- ``` Using this to get rid of formatting issues in certain text editors. -->

#### Syntax highlighting
GitHub provides `syntax highlighting` support which means that the content within a codeblock can be colorized, depending on what coding language was selected.

!!! note "Note"
    GitHub supports Diagrams from Mermaid.js.  
    To display a graph, use `mermaid` as the syntax highlighting and create the format you would use in Mermaid.js itself.

!!! example
    === "Markdown"
        ````markdown
        This here is some JSON with syntax highlighting:  
        ```json
        {
          "hello": "world",
          "how": [
            "are",
            "you?"
          ]
        }
        ```
        ````
        
    === "Result"
        This here is some JSON with syntax highlighting:  
        ```json
        {
          "hello": "world",
          "how": [
            "are",
            "you?"
          ]
        }
        ```

----
## Tables
Making tables in Markdown is fairly simple.

!!! example
    === "Markdown"
        ```markdown
        | Example      | One             |
        | ------------ | --------------- |
        | You can make | it look pretty! |
        
        Example | Two
        --- | ---
        Not so pretty... | Yet it still works.
        
        ----
        Text alignment.
        
        | Title 1 | Title 2                | Title 3   | Title 4       |
        | ------- |:---------------------- |:---------:| -------------:|
        | default | Left (Same as default) | Centered  | Right         |
        ```
        
    === "Result"
        | Example      | One             |
        | ------------ | --------------- |
        | You can make | it look pretty! |
        
        Example | Two
        --- | ---
        Not so pretty... | Yet it still works.
        
        ----
        Text alignment.
         
        | Title 1 { style="text-align: center;" } | Title 2 { style="text-align: center;" } | Title 3 { style="text-align: center;" } | Title 4 { style="text-align: center;" } |
        |-----------------------------------------|:----------------------------------------|:---------------------------------------:|----------------------------------------:|
        | default                                 | Left (Same as default)                  | Centered                                | Right                                   |

----
## Emojis
GitHub allows to render emojis.  
A emoji is defined using a starting colon (`:`) followed by any alphanummerical text, hyphens (`-`) and underscores (`_`) amd ends with anothor colon.

All available Emojis can be found on @ikatyang/emoji-cheat-sheet

!!! extensions "MkDocs Extensions"
    - [PyMdownX's Emoji Extension][emoji-extension]{ target="_blank" rel="nofollow" }

[emoji-extension]: https://facelessuser.github.io/pymdown-extensions/extensions/emoji/

!!! example
    === "Markdown"
        ```markdown
        Valid emoji:  
        :smile:
        
        Invalid emoji:
        :some emoji:
        ```
        
    === "Result"
        Valid emoji:  
        :smile:
        
        Invalid emoji:  
        :some emoji:

----
## Math expressions
GitHub supports the LaTeX format to display complex math expressions using normal text.  
To display an expression, surround the expression with either one or two dollar symbols (`$`) to indicate the start and end of an expression and render it inline or as separate block respectively.

!!! extensions "MkDocs Extensions"
    - [PyMdownX's Arithmatex Extension][arithmatex-extension]{ target="_blank" rel="nofollow" }

[arithmatex-extension]: https://facelessuser.github.io/pymdown-extensions/extensions/arithmatex/

!!! example
    === "Markdown"
        ```markdown
        Inline math: $\sqrt{3x-1}+(1+x)^2$
        
        
        Cauchy-Schwarz Inequality:
        
        $$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$
        ```
    
    === "Result"
        Inline math: $\sqrt{3x-1}+(1+x)^2$
        
        Cauchy-Schwarz Inequality:
        
        $$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

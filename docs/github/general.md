<!-- We have the links here because MkDocs doesn't like indended reference links -->
[Link]: https://google.com
[GitHub]: https://github.com

[github_logo]: https://github.andre601.com/GitHub-Markdown/assets/img/github.png

# General
This page lists all features that can be used across all places on GitHub, which support markdown formatting.

- [Headers](#headers)
- [Text formatting](#text-formatting)
    - [Italic](#italic)
    - [Bold](#bold)
    - [Strikethrough](#strikethrough)
    - [Combinations](#combinations)
    - [Quotes](#quotes)
    - [Horizontal rule](#horizontal-rule)
    - [Line breaks](#line-breaks)
- [Lists](#lists)
    - [Ordered](#ordered)
    - [Unordered](#unordered)
    - [Tasks](#tasks)
- [Links](#links)
    - [Normal](#normal)
    - [Reference](#reference)
    - [Image](#image)
- [Code](#code)
    - [Inline code](#inline-code)
    - [Code Block](#code-block)
        - [Syntax highlighting](#syntax-highlighting)
- [Tables](#tables)
- [Emojis](#emojis)

----
## Headers
Headers are larger text like shown above and also allow you to link to it, when used in Markdown files or the Wiki.

!!! info
    === "Markdown"
        ```
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

----
## Text formatting
GitHub offers normal Markdown formatting but also adds some own styling.

### Italic
You can display a text in italic by surrounding it either with a single asterisks (`*`) or underscore (`_`).

!!! info
    === "Markdown"
        ```
        You can use *asterisks* to make text *italic*.
        
        Alternatively can you also use _underscores_.
        ```
    === "Result"
        You can use *asterisks* to make text *italic*.
        
        Alternatively can you also use _underscores_

### Bold
Using two Asterisks (`*`) or two underscores (`_`) before and after the text makes it bold.

!!! info
    === "Markdown"
        ```
        You can use **two asterisks** to make text **bold**.
        
        Alternatively can you also use __two underscores__.
        ```
    === "Result"
        You can use **two asterisks** to make text **bold**.
        
        Alternatively can you also use __two underscores__.

### Strikethrough
This is a GitHub exclusive formatting code, where you use two tilde (`~`) before and after text to make it strikethrough.

!!! info
    === "Markdown"
        ```
        Don't like this text? Just ~~cross it out!~~
        ```
    === "Result"
        Don't like this text? Just ~~cross it out!~~

### Combinations
You can combine the above [formatting options](#text-formatting) to have more special text.

!!! info
    === "Markdown"
        ```
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

!!! info
    === "Markdown"
        ```
        Albert Einstein once said:  
        > Once you stop learning you start dying.
        ```
    === "Result"
        Albert Einstein once said:  
        > Once you stop learning you start dying.

### Horizontal rule
Using three or more hyphens (`-`), astersisks (`*`) or underscores (`_`) will create a horizontal rule (line) which goes accross the entire text area.

!!! info
    === "Markdown"
        ```
        Use three or more hyphens, asterisks or underscores to make a line
        
        ---
        But keep an empty line between text and the hyphens below it or it becomes a h2 header!
        ```
    === "Result"
        Use three or more hyphens, asterisks or underscores to make a line
        
        ---
        But keep an empty line between text and the hyphens below it or it becomes a h2 header!

### Line breaks
To indicate a line break end a line with two spaces (in our example indicated using a plus (`+`) symbol).

!!! note
    Issues and Pull requests don't require two spaces at the end for line breaks.

!!! info
    === "Markdown"
        ```
        We make line breaks, by ending a line with two spaces.++ <!-- + means a space -->
        This line will show below the other.
        
        For a new paragraph, leave an empty line in between.
        ```
    === "Result"
        We make line breaks, by ending a line with two spaces.  
        This line will show below the other.
        
        For a new paragraph, leave an empty line in between.

----
## Lists
You can have various types of lists to order things.

### Ordered
Starting a line with any number followed by a dot, space and text makes a new Ordered list.

!!! info
    === "Markdown"
        ```
        1. This is the first entry.
        2. This is the second one.
        4. The numbers don't even have to make sense!
        
        ----
        
        1. To indend an entry...
            1. ...add 2 spaces before it.
        ```
    === "Result"
        1. This is the first entry.
        2. This is the second one.
        4. The numbers don't even have to make sense!
        
        ----
        
        1. To indend an entry...
            1. ...add 2 spaces before it.

### Unordered
The unordered list has the same behaviour as the ordered list, with the difference that it doesn't use a number and dot, but instead either an asterisks (`*`) or a hyphen/dash (`-`)

!!! info
    === "Markdown"
        ```
        - This list
        - doesn't use numbers.
        
        ---- <!-- We use this to have the below list separated -->
        * Because it is
        * unordered.
        ```
    === "Result"
        - This list
        - doesn't use numbers.
        
        ---- <!-- We use this to have the below list separated -->
        * Because it is
        * unordered.

### Tasks
This is a GitHub exclusive feature, where you can make checklists using `- [ ]` as format.  
The "check" an entry, will you only need to replace the space in between the brackets with an x.

Note that MkDocs doesn't provide such a system by default, so we use PyMdown's Tasklist extension to simulate a similar behaviour.

!!! info
    === "Markdown"
        ```
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

#### Note about mixed lists
You can mix the different list types, but keep in mind that you will need to use 3 or 4 spaces to indent a List of a different type.

----
## Links
You can link to stuff in various ways

### Normal
Linking to a page normally is simple. Either post the link directly, or use `[text](link)`

!!! info
    === "Markdown"
        ```
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

!!! info
    === "Markdown"
        ```
        [Link]: https://google.com
        [GitHub]: https://github.com
        
        [Reference links][Link] can be used like that to link to sites like [GitHub]!
        ```
    === "Result"
        [Reference links][Link] can be used like that to link to sites like [GitHub]!

### Image
Images can be added the same way as links (including reference link-style), but have an exclamation mark (`!`) before them.

!!! info
    === "Markdown"
        ```
        [github_logo]: https://github.andre601.com/GitHub-Markdown/assets/img/github.png
        
        ![name][github_logo]  
        ![github_text](https://github.andre601.com/GitHub-Markdown/assets/img/github-text.png)
        ```
    === "Result"
        ![name][github_logo]
        
        ![github_text](https://github.andre601.com/GitHub-Markdown/assets/img/github-text.png)

----
## Code
GitHub supports inline code and code blocks with syntax highlighting.

### Inline code
To make inline code, surround the the text with a single backtick (`` ` ``).  

!!! tip "Pro-tip"
    If you want to display backticks within inline code will you need to start and end the text with **2 backticks**.

!!! info
    === "Markdown"
        ```
        This is text with some `inline code`.
        ```
    === "Result"
        This is text with some `inline code`.

### Code Block
Code blocks allow to display multi-line code and even have [syntax highlighting](#syntax-highlighting).  
To put text into a code block, surround it with three backticks (```` ``` ````).

!!! tip "Pro-tip"
    If you want to display three backticks within code blocks will you need to start and end the text with **4 backticks**.

!!! info
    === "Markdown"
        ````
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

!!! info
    === "Markdown"
        ````
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

!!! info
    === "Markdown"
        ```
        | Example      | One             |
        | ------------ | --------------- |
        | You can make | it look pretty! |
        
        Example | Two
        --- | ---
        Not so pretty... | Yet it still works.
        
        ----
        Text alignment.
        
        <!-- MkDocs also changes alignment of titles. This isn't the case with GitHub -->
        | Titles  | are                    | always    | centered      |
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
         
        | Titles  | are                    | always    | centered      |
        | ------- |:---------------------- |:---------:| -------------:|
        | default | Left (Same as default) | Centered  | Right         |

----
## Emojis
GitHub allows to render emojis.  
A emoji is defined using a starting colon (`:`) followed by any alphanummerical text, hyphens (`-`) and underscores (`_`) amd ends with anothor colon.

All available Emojis can be found on http://Emoji-cheat-sheet.com.

!!! info
    === "Markdown"
        ```
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

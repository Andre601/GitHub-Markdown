---
title: Markdown for Wikis
description: All the unique features for Wiki Pages.
hide:
- toc
---

[home]: https://github.com/Andre601/GitHub-Markdown/wiki

# Wiki
This page lists all features that can be used inside Wikis on GitHub repositories.

!!! info "Note"
    Wikis support all [general features](../general).

- [Reference links](#reference-links)

----
## Reference links
The wiki has its own unique type of reference links which is slightly different from the [other type](../general#reference).  
That said, are [all other link types](../general#links) still usable.

You can easly link to other pages by starting a link with two opening square brackets (`[`) followed by the page name and closing it with two closing square brackets (`]`).

!!! info
    === "Markdown"
        ```
        [[Home]]
        
        Displaying an alternative text:  
        [[Main page|Home]]
        ```
    === "Result"
        <!-- We have to cheat here a bit because there's no other way to link a wiki in MkDocs -->
        [Home]
        
        Displaying an alternative text:  
        [Main page][home]
---
title: Markdown for Wikis
description: All the unique features for Wiki Pages.
hide:
- navigation
- toc
---

[general]: https://andre601.ch

--8<-- "nav_wiki.txt"
    
# :octicons-book-16: Wiki
This page lists all features that can be used inside Wikis on GitHub repositories.

--8<-- "general_features.txt"

- [Reference links](#reference-links)

----
## Reference links
The wiki has its own unique type of reference links which is slightly different from the [other type](../general#reference).  
That said, are [all other link types](../general#links) still usable.

You can easly link to other pages by starting a link with two opening square brackets (`[`) followed by the page name and closing it with two closing square brackets (`]`).

!!! info
    === "Markdown"
        ```
        [[General]]  
        [[Issues Pull requests]]
        
        Displaying an alternative text:  
        [[Main Formatting|General]]  
        [[Issues and Pull request formatting|Issues Pull requests]]
        ```
    === "Result"
        [[General]]  
        [[Issues Pull requests]]
        
        <!-- The EzLinks plugin we use sadly uses a different order -->
        Displaying an alternative text:  
        [[General|Main Formatting]]  
        [[Issues Pull requests|Issues and Pull request formatting]]

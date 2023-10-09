---
title: Markdown for Wikis
description: All the unique features for Wiki Pages.
hide:
- navigation
- toc
---

[general]: https://andre601.ch
    
# :octicons-book-16: Wiki
This page lists all features that can be used inside Wikis on GitHub repositories.

--8<--
general_features.txt
toc.txt
--8<--

----
## Wiki Page links
The Wiki pages have a unique Link patternt that can be used to link to other pages on the Wiki (optionally with a separate text to display).  
Any other link type is also supported.

You can easly link to other pages by starting a link with two opening square brackets (`[`) followed by the page name and closing it with two closing square brackets (`]`).

!!! example
    === "Markdown"
        ```
        [[general]]  
        [[issues-pull-requests-and-discussions]]
        
        Displaying an alternative text:  
        [[Main Formatting|general]]  
        [[Issues, Pull requests and Discussions formatting|issues-pull-requests-and-discussions]]
        
        Link to a specific section in a page:  
        [[Reference Links|general#reference]]
        ```
        
    === "Result"
        [general](general.md)  
        [issues-pull-requests-and-discussions](issues-pull-requests-and-discussions.md)
        
        Displaying an alternative text:  
        [Main Formatting](general.md)  
        [Issues, Pull requests and Discussions formatting](issues-pull-requests-and-discussions.md)
        
        Link to a specific section in a page:  
        [Reference Links](general.md#reference)

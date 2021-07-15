---
title: Markdown for Issues, Pull requests and Discussions
description: All the unique features for issues, Pull requests and Discussions.
hide:
- navigation
- toc
---

[MagicLink]: https://facelessuser.github.io/pymdown-extensions/extensions/magiclink

--8<-- "nav_issues.txt"

# :octicons-issue-opened-16: Issues, :octicons-git-pull-request-16: Pull Requests and :octicons-comment-discussion-16: Discussions
This page lists all features that can be used across all issues, Pull requests and Discussions on GitHub.

--8<-- "general_features.txt"

- [Link shortening](#link-shortening)
    - [Commits](#commits)
    - [Issues and Pull requests](#issues-and-pull-requests)
- [File previews](#file-previews)
- [Color preview](#color-preview)
- [Advanced (task) Lists](#advanced-task-lists)

----
## Link shortening
GitHub automatically shortens/alters a list of specific URL-patterns to have it more easy to read.

### Commits
Posting a commit URL will automatically shorten it depending on some conditions.  
When the URL points to a commit in the same repo, will it be changed to the first 7 characters of the commit SHA.  
However, when the URL points to a commit of a separate repository, will the resulting text be in the form of `user/repo@ commit`

!!! tip "Pro-tip"
    You can also just provide the commit SHA in one of the following formats to link it:
    
    - `:commit` For commits within the same repository
    - `:user@:commit` For commits of User `:user`
    - `:user/:reopo@:commit` For commits of User `:user` in repo `:repo`

!!! example
    === "Markdown"
        ```
        Same repository:
        
        - https://github.com/Andre601/GitHub-Markdown/commit/97c92e943f888101026473b2168c90398d92655c
        - 97c92e943f888101026473b2168c90398d92655c
        
        Different repository:
        
        - https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e
        - jlord/sheetsee.js@a5c3785ed8d6a35868bc169f07e40e889087fd2e
        ```
        
    === "Result"
        Same repository:
        
        - [`97c92e`](https://github.com/Andre601/GitHub-Markdown/commit/97c92e943f888101026473b2168c90398d92655c)
        - [`97c92e`](https://github.com/Andre601/GitHub-Markdown/commit/97c92e943f888101026473b2168c90398d92655c)
        
        Different repository:
        
        - [jlord/sheetsee.js@`a5c3785`](https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e)
        - [jlord/sheetsee.js@`a5c3785`](https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e)

### Issues and Pull requests
You can link to issues and Pull requests in various ways.

!!! example
    === "Markdown"
        ```
        Full URL:
        
        - https://github.com/Andre601/GitHub-Markdown/pull/2
        - https://github.com/jlord/sheetsee.js/issues/26
        
        Issue/Pull request number (Own repository):
        
        - #2
        
        Issue/Pull request number (External repository):
        
        - jlord/sheetsee.js#26  
        - github/linguist#4039
        ```
        
    === "Result"
        Full URL:
        
        - [#2](https://github.com/Andre601/GitHub-Markdown/pull/2)
        - [jlord/sheetsee.js#26](https://github.com/jlord/sheetsee.js/issues/26)
        
        Issue/Pull request number (Own repository):
        
        - [#2](https://github.com/Andre601/GitHub-Markdown/pull/2)
        
        Issue/Pull request number (External repository):
        
        - [jlord/sheetsee.js#26](https://github.com/jlord/sheetsee.js/issues/26)
        - [github/linguist#4039](https://github.com/github/linguist/pull/4039)

----
## File previews
When you link to a section of a file in a specific commit will GitHub show the targeted content in the Issue/Pull request.

Note, that we use an image here to display the result.

!!! example
    === "Markdown"
        ```
        https://github.com/Andre601/GitHub-Markdown/blob/97c92e943f888101026473b2168c90398d92655c/requirements.txt#L1
        ```
        
    === "Result"
        ![image](file-preview.png)

----
## Color preview
When using [inline code](../general#inline-code) can you use a hashtag, followed by a hexadecimal color value (i.e. `#ffffff`) and GitHub will automatically add a small square in the provided color to it.

!!! example
    === "Markdown"
        ```
        I like green: `#16c60c`
        ```
        
    === "Result"
        I like green: `#16c60c🟩`

----
## Advanced (task) lists
Whenever you link an issue, Pull request or Discussion in a list or Task list will GitHub automatically display the title, id and the current state of the issue, Pull request or Discussion.  
Whenever a issue or Pull request is linked in a task list and said issue/Pull request is closed or merged will the corresponding task list entry get "checked".

!!! example
    === "Markdown"
        ```
        Representation not 100% accurate
        
        - [ ] #15
        - #16
        
        External repository:
        
        - https://github.com/github/feedback/discussions/4251
        ```
    === "Result"
        Representation not 100% accurate
        
        - [x] [:octicons-git-merge-16:{ .color-merged } **Replace info with example admonition** #15](https://github.com/Andre601/GitHub-Markdown/pull/15)
        - [:octicons-issue-opened-16:{ .color-opened } **Test linked PR** #16](https://github.com/Andre601/GitHub-Markdown/pull/16)
        
        External repository:
        
        - [:octicons-comment-discussion-16:{ .color-neutral } **The new Task List (Beta)** github/feedback#4251](https://github.com/github/feedback/discussions/4251)
        

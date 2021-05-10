---
title: Markdown for Issues/Pull requests
description: All the unique features for issues and Pull requests.
hide:
- navigation
- toc
---

[MagicLink]: https://facelessuser.github.io/pymdown-extensions/extensions/magiclink

--8<-- "nav_issues.txt"

# :octicons-issue-opened-16: Issues / :octicons-git-pull-request-16: Pull Requests
This page lists all features that can be used across all issues and Pull requests on GitHub.

--8<-- "general_features.txt"

- [Link shortening](#link-shortening)
    - [Commits](#commits)
    - [Issues and Pull requests](#issues-and-pull-requests)
- [File previews](#file-previews)
- [Color preview](#color-preview)

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

!!! info
    === "Markdown"
        ```
        Same repository:  
        https://github.com/Andre601/GitHub-Markdown/commit/97c92e943f888101026473b2168c90398d92655c  
        97c92e943f888101026473b2168c90398d92655c
        
        Different repository:  
        https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e  
        jlord/sheetsee.js@a5c3785ed8d6a35868bc169f07e40e889087fd2e
        ```
    === "Result"
        Same repository:  
        https://github.com/Andre601/GitHub-Markdown/commit/97c92e943f888101026473b2168c90398d92655c  
        97c92e943f888101026473b2168c90398d92655c
        
        Different repository:  
        https://github.com/jlord/sheetsee.js/commit/a5c3785ed8d6a35868bc169f07e40e889087fd2e  
        jlord/sheetsee.js@a5c3785ed8d6a35868bc169f07e40e889087fd2e

### Issues and Pull requests
You can link to issues and Pull requests in various ways.

!!! info
    === "Markdown"
        ```
        Full URL:  
        (Don't mind the number showing as `!2`. This is caused by [MagicLink]. GitHub usually displays `#2`)  
        https://github.com/Andre601/GitHub-Markdown/pull/2  
        https://github.com/jlord/sheetsee.js/issues/26
        
        Issue/Pull request number (Own repository):  
        <!-- To prevent #2 becoming a H2 header --> #2
        
        Issue/Pull request number (External repository):  
        jlord/sheetsee.js#26  
        github/linguist#4039
        ```
    === "Result"
        Full URL:  
        (Don't mind the number showing as `!2`. This is caused by [MagicLink]. GitHub usually displays `#2`)  
        https://github.com/Andre601/GitHub-Markdown/pull/2  
        https://github.com/jlord/sheetsee.js/issues/26
        
        Issue/Pull request number (Own repository):  
        <!-- To prevent #2 becoming a H2 header --> #2
        
        Issue/Pull request number (External repository):  
        jlord/sheetsee.js#26  
        github/linguist#4039

----
## File previews
When you link to a section of a file in a specific commit will GitHub show the targeted content in the Issue/Pull request.

Note, that we use an image here to display the result.

!!! info
    === "Markdown"
        ```
        https://github.com/Andre601/GitHub-Markdown/blob/97c92e943f888101026473b2168c90398d92655c/requirements.txt#L1
        ```
    === "Result"
        ![image](file-preview.png)

----
## Color preview
When using [inline code](../general#inline-code) can you use a hashtag, followed by a hexadecimal color value (i.e. `#ffffff`) and GitHub will automatically add a small square in the provided color to it.

!!! info
    === "Markdown"
        ```
        I like green: `#16c60c`
        ```
    === "Result"
        I like green: `#16c60c🟩`


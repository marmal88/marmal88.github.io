---
title: Thoughts on git workflow 
categories: 
  - terminal
  - git
---

So I've recently added 3 new plugins to my git workflow on vim. 

- Gitsigns - for highlighting changes in texts and to offer a view of file changes
- Neogit - for git workflow 
- DiffView - for handling merge changes

I thought these plugins made working with git more intuitive on the terminal.

## Gitsigns
This is a plugin renders the uncomitted changes made on your file and comes with several useful other tools to navigate commits and view the git tree.

<img src="/assets/images/posts/gitsigns_blame.png" alt="gitblame"/>

An unexpected workflow combination that turned out to be useful was using `:Gitsign diffthis` in combination with `MarkdownPreview`.

`Gitsigns` shows the difference between the un-commited stage and current state, and the `Markdown Previewer` renders the markdown in the browser. 

## Neogit
Initially I was quite hesitant of installing a plugin for git workflow, as I felt that I didn't want to lose touch of typing the actual git commands in the terminal. 

However, I realized that there were a whole bunch of git commands that I would not have bothered with if i was not using neogit. 

For example, being able to commit just the lines that I want instead of commiting the entire file is now easily done via vim `Visual` mode line selection.

![commiting to git by line](/assets/images/posts/neogit_line_commit.png)

Another bug bear was not being able to preview git stash easily. Now with the inbuilt previewer I can quickly view stashed changes and make a decision on which stash I would like to keep.

Also other functions that are more complicated and would typically require more complex commands are now available via a simple interface with minimal overhead.

- Cherry-picking commits
- Tagging and revisions
- Managing upstream and remote changes

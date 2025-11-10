---
title: Managing marks in neovim 
categories: 
  - terminal
  - marks
---

One issue I had when switching to neovim was the inefficiency in switching tabs and moving quickly across files.

For example, if i was working on a certain function in python that spanned 2 files, I typically had both open in a vertical split.

But this creates issues when there are more than 2 files or when the codebase is large and the 2 locations on the same file are far apart.

One way of solving it is to use folds, but sometimes this hides details that might be important.

Since we already have a mental map of the sections that are required, The easier way would be to have a way of navigating across these points.

That's when I encountered neovim's `marks`.

But.. there are also issues with marks:

- By default `marks` are invisible on neovim, hence you need a way to search/preview them
- Navigating Marks across different files and buffers is non native to neovim
- Managing global and buffer `marks` are also an issue 

Enter the `marks` plugin!, documentation [here](https://github.com/chentoast/marks.nvim). 

With this plugin marks are notated in the gutterline with their mark prefix!

Other than this visual change, The use of the shortkeys have also altered my workflow:

- `ma` to set mark to `a`
- `dma` to remove mark `a`
- `dm-` to delete marks on the current line
- `dm<space>` to remove all local marks in buffer
- `\^` to move to the last edited line
- `m]` instead of `]'` to move the the next mark 
- `m[` instead of `['` to move to the previous mark 
- `m:<mark>` opens a buffer to preview mark

I think that this resolves most of the issues that I have with marks.

For the below items, here are my workarounds..

- Deletion of global marks - `:delm A-Z0-9`


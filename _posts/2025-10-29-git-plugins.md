---
title: Thoughts on git workflow 
categories: 
  - terminal
  - git
---

So I've recently added 4 new plugins to my git workflow on vim. 

- Gitsigns - for highlighting changes in texts and to offer a view of file changes
- Neogit - for git workflow 
- DiffView - for handling merge changes
- Lazygit - integrated UI for more complicated git workflows

I thought these plugins made working with git more intuitive on the terminal.

## 1. Gitsigns
This is a plugin renders the uncomitted changes made on your file and comes with several useful other tools to navigate commits and view the git tree.

<img src="/assets/images/posts/gitsigns_blame.png" alt="gitblame"/>

An unexpected workflow combination that turned out to be useful was using `:Gitsigns diffthis` in combination with `MarkdownPreview`.

`Gitsigns` shows the difference between the un-commited stage and current state, and the `Markdown Previewer` renders the markdown in the browser. 

## 2. Neogit
Initially I was quite hesitant of installing a plugin for git workflow, as I felt that I didn't want to lose touch of typing the actual git commands in the terminal. 

However, I realized that there were a whole bunch of git commands that I would not have bothered with if I was not using neogit. 

Anyway, I can and still use the terminal quite often to commit and make changes as its become muscle memory by now.

Some of these git commands that were originally troublesome to remember include the below:

- Cherry-picking commits
- Viewing git stash and managing stash over time
- Tagging and managing tag revision both local and remote
- Managing upstream and remote changes
- Amending past commits

For example, being able to commit just the lines that I want instead of commiting the entire file is now easily done via vim `Visual` mode line selection.

![commiting to git by line](/assets/images/posts/neogit_line_commit.png)

The ease of executing commands that are harder to remember makes me more confident of using git and exploring it's various functions rather than memorizing boilerplate git code.

## 3. Diffview
Diffview is the plugin I use to manage merge conflicts and view code changes over time.

To toggle between opening and closing the diffview window, I have mapped the following keybindings.
```
vim.keymap.set('n', '<leader>dv', function()
	if next(require('diffview.lib').views) == nil then
		vim.cmd('DiffviewOpen')
	else
		vim.cmd('DiffviewClose')
	end
end, { desc = 'Toggle Diffview' })
```

### 3.1 Merge conflicts
For merge conflicts the 3-way diff view provides an interface to manage merge conflicts

### 3.2 File History
Another feature that I use often is to review the current file history using `DiffViewFilehistory <file>` and search into the previous git changes of the file.

By binding this keymap and reviewing files often , I realized that I keep better commits over time and am able to review them better over time.

```
vim.keymap.set('n', '<leader>dh', '<CMD>DiffviewFileHistory<CR>', { desc = 'View file history' })
```

### 3.2 Viewing differences between specific commits 
Another workflow that works for me is to run `git log --oneline` to obtain the specific commit hash.

I'll then check the difference between this file and the others using `:DiffViewOpen <commit-hash>`. 


### 4. Lazygit
This is really more of a preference thing, but I realized that I am inclined to use the more verbose git commands like interactive rebase and cherry-pick when using lazygit.

This plugin allows me to write more concise commits and make the overall PR somewhat more understandable. 



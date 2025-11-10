---
title: Installing Markdown Previewer 
categories: 
  - terminal
  - markdown
---

So I recently installed the markdown-preview plugin ['link']('https://github.com/iamcco/markdown-preview.nvim'). 

However, I since I was on the latest version of neovim v0.12.0 at the time of writing the installation documentation was abit old.

Here is the code that I used to install the yarn and npm dependencies. 

```bash
cd ~/.local/share/nvim/site/pack/packer/start/
git clone https://github.com/iamcco/markdown-preview.nvim.git
cd markdown-preview.nvim
npx --yes yarn install
npx --yes yarn build
```

Through this exercise I also realized that the location where the dependencies files were being stored, which was at this location `~/.local/share/nvim/site/pack/core/opt`.

After which you can just add the relavant configuration options to the base `init.vim` file.

```vim
let g:mkdp_auto_start = 1
let g:mkdp_auto_close = 1
let g:mkdp_port = '5555'
let g:mkdp_filetypes = ['markdown']
```

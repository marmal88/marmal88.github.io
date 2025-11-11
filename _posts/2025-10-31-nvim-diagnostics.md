---
title: Diagnostics in nvim 
categories: 
  - terminal
  - language-servers
  - diagnostics
---

Neovim's internal diagnostic tool `vim.diagnostic` is a framework for diagnostic producers to report diagnostics [link](https://neovim.io/doc/user/diagnostic.html).

Since Neovim v0.11+, the way to configure language servers has moved from the legacy `require('lspconfig')` to `vim.lsp.config()` & `vim.lsp.enable()`.

This removes the need to install `nvim-lspconfig` package and in my opinion simplifies the process to get started with language servers. 

## Tiny inline diagnostic

While the Neovim does support inline citaton the difference is documented [here](https://github.com/rachartier/tiny-inline-diagnostic.nvim?tab=readme-ov-file#comparison-with-neovims-built-in-virtual_lines)

I installed the plugin `tiny-inline-diagnositic` due to ability to keep the diagnostic message compact and show the issues when I am on that line.

The lack of clutter leads to better clarity when writing code and triaging of issues.

To use this diagnostic tool you first need to switch off the `virtual_text` in the native inline diagnostics

```lua
vim.diagnostic.config({
	underline = true,     -- set underline for offending line to true
	virtual_text = false, -- set virtual_text as false
})
```

![virtual text](/assets/images/virtual_text.png)

Then set the configs necessary for the `tiny-inline-diagnositic` plugin.

```lua
require('tiny-inline-diagnostic').setup({
	preset = 'ghost',                              -- icons set to ghosts
	options = {
		add_messages = { display_count = true },   -- additional messages count of errors encountered on line
		show_source = { enabled = true },          -- show the source of the error
		multilines = { enabled = true },           -- additional messages to bleed over to next line
	},
	blend = { factor = 0.2 },                      -- visbility of diagnostic
})
```
Once created the plugin will show as below
![inline diagnostic](/assets/images/inline_diagnostic.png)



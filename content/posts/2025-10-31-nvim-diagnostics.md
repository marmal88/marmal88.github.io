---
title: Diagnostics in nvim 
categories: 
  - terminal
  - language-servers
  - diagnostics
---

Neovim's internal diagnostic tool `vim.diagnostic` is a framework for diagnostic producers to report diagnostics [link](https://neovim.io/doc/user/diagnostic.html).

Since Neovim v0.11+, the legacy way to configure language servers has moved from `require('lspconfig')` to `vim.lsp.config()`. 

This change has 


## Inline diagnostic

While the Neovim does support inline citaton the difference is documented [here](https://github.com/rachartier/tiny-inline-diagnostic.nvim?tab=readme-ov-file#comparison-with-neovims-built-in-virtual_lines)

To use this diagnostic tool you first need to switch off the 

![inline diagnostic](/assets/assets/images/inline_diagnostic.png)

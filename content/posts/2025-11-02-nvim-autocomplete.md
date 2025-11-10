---
title: Managing autocompletion neovim 
categories: 
  - terminal
  - autocompletion
---
> Notice:
Please ensure that you have already installed your language servers before working on autocompletion.

There are quite a number of plugins available for autocompletion in neovim.

I chose `blink.cmp` due to its rust implementation and the high number of possible configurations that you can have with it, more on that later.

I've broken down this article to better remind me of how to get this setup for the first time.


## 1. Installation of Blink CMP using Vim Pack

As you will need rust to get the most of `blink.cmp`, you can install it using the instructions below.

```bash
# Install Rust 
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
After adding the package to `vim.pack`, go to the location `~/.local/share/nvim/site/pack/core/opt/blink.cmp` here is where the neovim packages are installed.

You can then compile the package in release mode using the command `cargo build --release`.

## 2. Blink CMP Configuration
The `blink.cmp` documentation lays out the clearly the key sections of the config. 

You can check out the documentation [here](https://cmp.saghen.dev/configuration/general.html).

| No. | Options | Description | 
| --- | --- | --- |
| 1. | Appearence | Customize the appearence of the menu window |
| 2. | Completion | Customize the look and feel of the completions themselves |
| 3. | Fuzzy | Preference for `rust` or `lua` as completion mechanism |
| 4. | Signature | Provides completions for defined functions |
| 5. | Sources | Preference for source of completions |
| 6. | Snippets | Customize snippets taken from ./snippet folder |


### 2.1 Appearence 
Configs for the appearence of the icons and sections are here

### 2.2 Completion
This is the heart of the autocompletion.

Here you can configure the look, feel and shortkeys for the autocompletion. 

This section is broken down into the following key sections and you can configure how you wish each one to behave.

| Sections | Description|
| -------- | ---------- |
| menu | Snippet menu settings |
| documentation | Documentation menu settings |
| ghost text | Hints for next incoming word |
| list | Behaviour when selecting into menu |

Do remember that you want to configure something that works for your workflow across languages.

### 2.3 Fuzzy
This is where you configure the type of completion engine (either `rust` or `lua`) that you want. 

If you choose `rust`, do note that the implementation engine is Frizbee. Docs are [here](https://github.com/saghen/frizbee)

Please see the instructions [here](#installation-of-blink-cmp-using-vim-pack) and the docs [here](https://cmp.saghen.dev/configuration/fuzzy.html#rust-vs-lua-implementation)

### 2.4 Signature
I found this to be really useful especially for cases where the you are unfamiliar with the function syntax. 

The if declared the function signature will provide you with the type and arguments accepted for the function.

![signature](/assets/images/posts/function_signature.png)

### 2.5 Sources
Here you can configure the priority of the autocompletion.  

### 2.6 Snippets
With `blink.cmp` you have the option to use `friendly-snippets`, which is a maintained repo of code snippets. 

However, as the repository also contained included languages that I didn't personally used, I decided to copy the files from [there](https://github.com/rafamadriz/friendly-snippets/tree/main/snippets), only for the languages that I commonly used.

Just put them in the `~/.config/nvim/snippets` folder of your directory and `blink.cmp` will source it from there.

After which you can configure your present snippet engine in this case I used `mini-snippets`, which has extensive documentation. 







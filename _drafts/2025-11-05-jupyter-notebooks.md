---
title: Jupyter notebooks and Neovim
categories: 
  - terminal
  - jupyter-notebook
---

Native neovim support for Jupyter notebooks is not great.

Considering how neovim's design was centered around the terminal, the idea of moving to the browser for development work sounds counterintuitive.

While I rarely use notebooks nowadays, I recently had to run a notebook for to evaluate some data science work.

This led me to explore the different plugins available for Jupyter in neovim.

## 1. Jupyterlab

This would be the vanilla Jupyter lab instance in neovim. 

By serving the notebook in the browser one loses the keybindings that are native to the IDE, not to mention that jupyterlab is quite a large dependency.

However, this is the fastest way out of the box to get going.

```bash
# Serve the jupyter notebooks using the command
uvx jupyter lab
```

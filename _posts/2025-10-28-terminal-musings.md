---
title: My thoughts on terminals and terminal configurations
categories: 
  - terminal
  - wezterm
---

What people need or expect from their terminals can be rather subjective depending on what you primarily use it for.

For example, for application developers who use an IDE as their main driver might see the terminal as just a place to run their scripts or to install system-wide packages.

This is in contrast to DevOps or MLOps engineers who manage multiple VM's and do not want to lose their sessions when they move from one system to another.

As I maintain a homelab, I was looking for a quick and easy way for me to connect to that instance over SSH and be able to pick up easily when i left off. I also wanted to maintain the same look and feel and keybindings across the various environments that I was connected to. This led me to the Wezterm terminal.

While this is not an introduction to the terminal itself, you can read more [here](https://wezterm.org/index.html). 

I found the following features to be personally useful:
    - You can do multiplexing using the command `wezterm connect <device>`
    - Able to maintain my own keybindings in code. Brownie points for lua as i can use the same languages as my vim configs
    - GPU enabled hence able to look at images using `wezterm imgcat`



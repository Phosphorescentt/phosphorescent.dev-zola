+++
title = "Vim :g command"
date = 2025-05-28

[taxonomies]
tags=["til", "vim", "neovim"]
categories=["blog"]
+++

I have been using some variation of Vim on and off since ~2012. And in that time I have
learned staggeringly little about the editor. In comes [Vim
Golf](https://www.vimgolf.com/).

Long story short, today I learned about the `:g` command. `g` is short for global and
lets you run an `Ex` command across all lines matching some pattern in your current
buffer. This can be used to quickly do things like:

- Delete all blank lines: `:g/^\s*&/d`.
- Delete all lines containing only Python comments: `:g/^\s*# */d`.
- Copy all lines matching the pattern to register `a`: `qaq:g/pattern/y A` (where `qaq`
starts recording a macro into register `a` and immediately exits, leaving `a` empty and
`y A` appends to register `a` each line matched)

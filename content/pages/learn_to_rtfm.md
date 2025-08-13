+++
title = "Learn to RTFM!"
date = 2025-08-13

[taxonomies]
tags=["vim", "neovim", "productivity"]
categories=["blog"] 
+++

I spent a bunch of time unemployed this year (thanks redundancy). So I redid my
dotfiles. Goodbye AstroNvim, hello `init.lua`. I had two motivations for doing this:
1. I didn't understand what AstroNvim was doing to implement all this functionality, and
   when I wanted to add new things I always found it confusing.
1. [Vimothée Chalamet](https://www.youtube.com/@sylvanfranklin/videos) reignited my love
   for Vim and it's myriad of well thought out and modular features.

Now I am running nightly Neovim, using the inbuilt package manager for a select few
plugins and I have a single `init.lua` which I constructed entirely myself. And the
thing that enabled me was `:h`.

`:h` is (neo)vim's inbuilt help command. Typing `:h i` brings up some *very* extensive
documentation about what the `i` character does, and it puts it in the context of other
similar commands. Obviously I knew about `:h` before, but I never really understood how
to parse the information that was on my screen.

Having now written a little bit of lua and done some fiddling with a full config myself,
these `:h` pages are a goldmine. The combination of having *extremely* detailed docs for
a specific command, surrounded by other similar commands is incredible. Want to know how
to open a terminal buffer? `:h terminal`. Read a few sentences and scroll a bit and now
you know how to open a terminal buffer and what the keybinds are to perform actions in
it. All of that, for free, built into your editor, and it's completely offline.

I now feel much more confident with configuring my editor and I rarely feel like I have
to consult a search engine to get my answers. I wish I'd invested in this skill sooner,
I could've saved myself so much time.

You should learn to read the manual for your favourite tools too.

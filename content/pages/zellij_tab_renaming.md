+++
title = "Automatically rename Zellij tabs with Nushell"
date = 2025-06-07
updated = 2025-06-07

[taxonomies]
tags=["zellij", "nushell", "ricing"]
categories=["blog"] 
+++

Unfortunately I have a crippling issue with doing ungodly amounts of terminal futzing
instead of actually doing the stuff that I should be doing. To that end, I have just set
up automatic tab renaming for Zellij with Nushell and it was remarkably easy.

[Zellij](https://zellij.dev/) is a modern alternative to tmux/screen and I'm a real
sucker for something modern and written in rust. Out of the box, Zellij has a lot of
really cool functionality, but I'm a tmux girlie. My Zellij config is very minimal to
make all the keybinds similar to tmux, the only thing that's missing is the automatic
tab renaming.

A quick search about automatically renaming tabs in Zellij led me to [this
article](https://haseebmajid.dev/posts/2024-07-26-how-i-configured-zellij-status-bar/).
The author of this post shows two functions they have added to their fish setup. In
short, this setup uses Zellij's CLI utility to update the title of the tab using fish's
`fish_preexec` and `fish_postexec` hooks. In particulary it's issuing a `zellij action
rename-tab <tabname>`.

Nushell also has similar functionality to fish in it's
[hooks](https://www.nushell.sh/book/hooks.html#hooks). Combining all this together, we
can configure a couple of hooks to rename Zellij tabs wheneve we do something in the
command line. This gives us something like this:

```nu
$env.config = ($env.config | upsert hooks {
    pre_prompt: [ { 
        zellij action rename-tab "nu";
    } ]
    pre_execution: [ { || 
        mut repl_commandline = (commandline)
        if ($repl_commandline | str length) > 15 {
            $repl_commandline = ($repl_commandline | str substring 0..14) + "..."
        }
        zellij action rename-tab ($repl_commandline)
    } ]
})
```
The `pre_execution` hook is what lets us get a string value of the command currently
being run and `pre_prompt` resets the tab name back to "nu" every time we return to the
repl. The only special thing of note here is the call to `str substring 0..14` which just takes
the first 15 characters of the command being issued - just to make sure we don't end up
with silly long tab names.


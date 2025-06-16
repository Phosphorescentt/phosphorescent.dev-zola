+++
title = "Table of Contents Shortcode for Zola"
date = 2025-06-16

[taxonomies]
tags=["zola", "tera"]
categories=["blog"] 
+++

To build this website, I'm using a tool called [Zola](https://www.getzola.org/). For my
longer posts, I'd like to have a table of contents somewhere on the page for easier
navigation, but I don't want it on every page. This could've been achieved by making a
separate template for the page with a table of contents, but I wanted something a bit
more flexible that lets me insert the table of contents wherever I want. Apparently
there's not an easy way to do this, so I've come up with a bit of a hack based on an [old
GitHub issue](https://github.com/getzola/zola/issues/584).

Zola has functionality called
[shortcodes](https://www.getzola.org/documentation/content/shortcodes/) which lets you
call functions to insert text into your markdown before rendering the markdown into into
HTML. Unfortunately, because shortcodes are expanded *before* the markdown is parsed,
they don't have access to the attributes of the page. These attributes are exposed at
the template level, but not the shortcode level. So we have to do some tomfoolery. 

If we create a shortcode called `toc` that accepts no arguments and returns a constant
string `<!-- toc -->`, we can then replace that string with a call to a [Tera
macro](https://keats.github.io/tera/docs/#macros) that actually generates the HTML for
the table of contents. A specific implementation of method can be found in [this
commit](https://github.com/Phosphorescentt/phosphorescent.dev-zola/commit/5fb8df16284563c74ee17c43118658f954e686a4#diff-ec96e0fc2f34ad383e10ee3af3c78f2ec64cdf16eba5352cc184f01802f950c9).

Now when we write some markdown, we can insert `toc()` surrouneded by double curly
brackets wherever we want, and we will get a table of contents rendered correctly.
Below is an example of what the table of contents for this website will look like.

{{ toc() }}

# Header 1
## Subheader 1
## Subheader 2
## Subheader 3 
# Header 2
## Subheader 4


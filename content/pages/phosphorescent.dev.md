+++
title = "phosphorescent.dev"
date = 2025-03-27
updated = 2025-06-06

[taxonomies]
tags=["tailwind", "zola", "tera"]
categories=["projects"]
+++

# Overview

This website is the first project that I am documenting here. At present, it looks very
primitive and untidy which is because it is. I haven't touched any front end in a long
time as I have mostly been data engineering with Python. So why not do a little side
project to show off my work and develop some new skills?

# Tech Stack

This site is generated from a set of markdown documents and
[Tera](https://keats.github.io/tera) templates using [Zola](https://www.getzola.org/).
The styling is mostly done with [Tailwind](https://tailwindcss.com/) as I've heard good
things about it from colleagues & peers. My final verdict on it remains to be seen, but
my first impressions are good. I haven't quite figured out where I want to host this
site yet, but the easiest place is probably GitHub pages.

# Philosophy

I picked something simple and rolled my own theme for Zola so that I don't get tied into
some specific way of thinking. I want to be able to share stuff in whatever way makes
the most sense for me and my use case so having someone else decide for me seems wrong.

# Future Improvements

- [x] Find out if I can specify a different template on a per page basis. This would let
me use taxonomies instead of folders, but i want to be able to have diff formatting per
term in a `category` taxonomy.
- [x] Find a nice way to add in a [table of
contents](https://www.getzola.org/documentation/content/table-of-contents/).
- [ ] Make the tags on the post page look nicer.
- [ ] Sort links on home page by relevant attribute from section.
- [ ] Limit links on home page to highest 10-20.
- [x] Make it clear when one link on the home page ends and another one begins (cards or
something).
  - This has been done by adding dates. I'm not the biggest fan of this solution, but
  it's better than nothing.
- [x] Make styling consistent across the entire website (currently I am just doing
whatever feels good and works).
- [x] Mobile.
- [x] Populate the website with some real content.
- [x] Add dates to pages listed in taxonomies.
- [ ] Make the `taxonomy_list.html` template prettier. 

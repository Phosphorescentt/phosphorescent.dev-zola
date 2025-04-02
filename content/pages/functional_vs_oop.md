+++
title = "Functional programming streamlines additional behaviour"
date = 2025-03-27
[taxonomies]
tags=["functional", "oop"]
categories=["blog"]
+++

Below is a quote I found from an [article on the visitor pattern](https://chelseatroy.com/2021/05/01/building-an-interpreter-the-visitor-pattern/):

> Bob explains that we have two ways to orient our code. We could do it with objects, by having each of these expressions represented as classes handling all their own operations, or we could do it with functions that switch their behavior based on which type of expression they have been passed. The former (object) pattern makes it less work to add a new expression class and more work to add a new behavior, since we have to crack open every existing class to do it. The latter (functional) pattern makes it less work to add a new behavior, since we just need to write a new function without changing existing code. Adding a new expression, though, means cracking open all the existing functions and adding a case to each.

This is a summary of functional vs object oriented approaches that I haven't seen before. This perspective helps me explain _why_ I prefer functional approaches to solving software problems as opposed to object oriented ones: my (admittedly limited) professional experience to date has shown me that underlying data models don't change that much, but the behaviour often does.

With this in mind, it seems clear to me that we should adopt some of functional approaches to solving problems as it gives us more agility when the product requirements aren't very well defined, but the shape of the data is. Of course, if you know that your behaviour is unlikely to change very much, but your model space isn't well understood then perhaps an object oriented approach will work better.

This is all personal opinion from someone who has been data engineering for most of their career so take this interpretation with a pinch of salt.

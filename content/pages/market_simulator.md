+++
title = "Market Simulator"
date = 2025-05-05
updated = 2025-05-07

draft = true

[taxonomies]
tags=["rust", "markets", "finance"]
categories=["projects"]
+++

In this project, I implement a financial market simulator. The simulator allows custom
behaviour definitions for actors in the market and different exchange order matching
algorithms.

# Motivation

The main motivator for this project is to give me an opportunity to get dug into a
longer-term Rust project by doing something that is relatively simple to get started
with, but has a lot of potential areas for growth. This means that as my Rust skill
increases, I can start including more and more features. In particular, I could do some
fun things like:

- WASM bindings for actor and exchange behaviours in the market.
- GUI frontend to display market movements in real time.
- Multithreading.
- Backtesting engine for each actor's strategies based on saved market data from
previous simulations.
- Derivative products.

...and probably many, *many* more. The idea of this project is just to start writing
something and see where I feel like heading. If I want to hone some performance skills
and learn about multithreading then I can do that, but if I feel like playing around
with ideas for strategies, I can do that too!

# Concepts
In the current implementation, there are three main concepts:

**Actor**: This is an actor in the market that is interested in buying and selling goods
from other actors.

**Exchange**: An entity that facilitates the storage and matching of bid and ask orders
between different counterparties.

**Engine**: The part of the program that coordinates actions produced by actors and
exchanges and moves data between the two. 

# Behaviour

Currently the internals of this project are pretty simple and cut out a lot of the
complexities of actual financial markets, but this is to make the initial implementation
easier.

At the start of the program, an `Engine` must be created and a number of `Actor`s and
`Exchanges` must be registered with that engine. When creating the engine, the user mus
specify how many discrete time steps they want the simulation to run for. From the
`Engine`'s perspective each time step is broken into a few sub-steps:

- Actor Update: Each actor is updated with events produced by exchanges in the previous
  step.
- Actor Action: Each actor is asked for their action for this time step.
- Exchange Matching: Each exchange is asked to perform it's matching algorithm on the
bid and ask orders that it currently has.

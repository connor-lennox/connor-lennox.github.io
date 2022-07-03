---
title: Projects
---

These are just a few of the projects I've worked on. I'm notorious for not finishing the things I've started ([evidence on my Github](https://github.com/connor-lennox)), but the projects listed here are more or less complete.

# [Autofloss](https://connorlennox.com/autofloss)

I figure the best way to learn cross stitch is to start by developing an application which converts images and photographs into cross stitch patterns. So, I built *autofloss*, which is an in-browser way to make cross stitch patterns from uploaded images.

The image creation process is interesting because we are restricted to using colors available for purchase. The most common manufacturer of cross stitch thread (often called "floss") I found referenced online was DMC, so I loaded the full catalogue of DMC floss colors (about 500) as available colors for image building. I developed a greedy algorithm for optimizing color selection based on reducing entropy between a working state and a downsampled version of the target image.

This was my first foray into using React, so most of my development time was spent making a decent looking UI, managing application state between components, and providing useful things such as downloading a finished pattern for later use. The actual image solver was finished in an evening!

If you'd like to give it a try, it's [available online here!](https://connorlennox.com/autofloss). If you'd like to see how I made it, the source code is [also available online at Github.](https://github.com/connor-lennox/autofloss)

# Emulators

Some old video games are pretty fun, but it's a pain to actually set up the consoles needed to play them. Emulation takes this old hardware and replaces it with software, so that it can run on a computer (much more powerful than an NES). I've done a few projects regarding emulation, mostly working in Rust as it's a great language for this type of thing.

## Rust-Chip
The CHIP-8 was never a real console, rather an interpreter that ran on the COSMAC-VIP computer. That being said, due to its relative simplicity (only 35 opcodes in total) it serves as the "Hello World!" of emulator development. My CHIP-8 intepreter is written in Rust, and served as my first foray into the language. The data-driven and functional approach to Rust lends itself well to emulation, since the main process of emulation consists of modeling the state changes in the original device due to the loaded program and user input.

This project is available [on GitHub](https://github.com/connor-lennox/rust_chip), and is capable of running CHIP-8 games (a few are provided in the repo). The README of this repo is very detailed and goes into the specifics of how each component is emulated. If you're interested in how the CHIP-8 worked or how I simulate it, I recommend giving that a read.


## rGBL
For my first "real" emulator project, I built an emulator for the Nintendo Gameboy DMG. This is quite a bit more complex than the CHIP-8, since the Gameboy was real hardware with real specifications (and a considerable amount of undocumented and undefined behavior). My general approach to this project was to emulate each component individually, then combine them similar to how the Gameboy itself worked.

Thanks to others who have tackled this project before, there is a good amount of documentation available online regarding how the Gameboy works and the subtleties of its operation. This is incredibly useful for emulator development, because it means I don't have to completely reverse-engineer the original hardware (and instead I was able to implementing a software version of it).

The source code for my Gameboy emulator is [available here](https://github.com/connor-lennox/rgbl).

# Gamejams

A gamejam is an event where participants get anywhere from a couple days to a full month to build a game from scratch. While usually these are judged, it's more about the experience and having an incentive to finish a small project.

I've participated in a few jams over the past few years. The games I made are available to [play online and download here](https://tripleseven.itch.io).

# StockReduction

A decidedly mediocre chess engine that plays using the smallest possible search tree. Traditional chess engines look 20+ moves into the future, mine looks 2. I can get away with this because instead of using a static evaluation function I instead use a neural network to evaluate the position. The neural function itself is trained to predict what Stockfish (a classical chess engine) will think about a position after performing its deep search. This is a sneaky way to get the performance of a traditional model while keeping the search space relatively small.

Of course, there's a trade-off in the quality of the engine. If you'd like to try playing against it, [take a look at the Github repo](https://github.com/connor-lennox/StockReduction). If instead you'd like to read more about how it works, maybe [give the report a read](/other/stock-reduction.pdf).
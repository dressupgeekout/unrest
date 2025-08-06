# Unrest

This is dressupgeekout's fork of _Unrest_, a story-based RPG developed by
Pyrodactyl Games, optimized for Unix-like systems.

This versions provides a streamlined edition of the
[original source code](https://github.com/arvindrajayadav/unrest)
with the following changes:

- A Makefile for straightforward compilation
- Support for newer versions of Boost
- No support for macOS or Windows
- No support for mobile platforms
- No support for the Steam API

As with Pyrodactyl's original source distribution, this repository does not
come with the game data. Please purchase a copy of _Unrest_ in order to
actually play the game.


## How to build

First, make sure you have installed all the dependencies:

- `SDL2`, `SDL2_image`, `SDL2_mixer`, `SDL2_ttf`
- Boost
- GNU Make

Now you should be able to build. Make sure to substitute `make` for `gmake`
in case your OS uses BSD make(1) by default.

```
cd CRAB
make
```

If you think you might need them, you can provide extra C++ compiler flags like
this:

```
make EXTRA_CXXFLAGS=-I/usr/pkg/include
```

Next, you may install the program to the final destination. The usual
options for modifying the installation directories are available. Here are
the default values:

```
make install [PREFIX=/usr/local] [BINDIR=bin] [DESTDIR=/]
```

# `FX2D`

This repository contains the JavaFX renderer for Processing 4, also known as `FX2D`.

The JavaFX binaries have grown very large in size so this was a necessary step to avoid making the Processing download excessively large, given that not everyone uses JavaFX. More discussion/explanation [here](https://github.com/processing/processing4/issues/348).

This version of the JavaFX library will be required for `FX2D` sketches starting with 4.0 beta 4.


## Download Size

The build script creates a very large download (hundreds of megabytes), because Processing supports several platforms (3 officially, 3 more unofficially) and we want to make it easy to use all of them. This is an acceptable tradeoff for a standalone library like this, but if you want a smaller build, you have options:

1. Disable `<antcall target="retrieve-gluon">` stanzas for platforms you don't care about.

2. Un-comment the `<!-- <exclude name="**/*jfxwebkit.*" /> -->` line so that the WebKit library is removed.

These are not done by default because we've seen projects that (1) run on all those platforms, and (2) use the full browser implementation available with the WebKit support. Again, because this is an optional download, this seems the correct tradeoff.

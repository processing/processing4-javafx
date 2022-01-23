# `FX2D`

This repository contains the JavaFX renderer for Processing 4, also known as `FX2D`.

The JavaFX binaries have grown very large in size so this was a necessary step to avoid making the Processing download excessively large, given that not everyone uses JavaFX. More discussion/explanation [here](https://github.com/processing/processing4/issues/348).

This version of the JavaFX library will be required for `FX2D` sketches starting with 4.0 beta 4.


## This library is large

The build script creates a very large download (hundreds of megabytes), because Processing supports several platforms (3 officially, 3 more unofficially) and we want to make it easy to use all of them. This is an acceptable tradeoff for a standalone library like this, but if you want a smaller build, you have options:

1. Disable `<antcall target="retrieve-gluon">` stanzas for platforms you don't care about.

2. Un-comment the `<!-- <exclude name="**/*jfxwebkit.*" /> -->` line so that the WebKit library is removed.

These are not done by default because we've seen projects that (1) run on all those platforms, and (2) use the full browser implementation available with the WebKit support. Again, because this is an optional download, this seems the correct tradeoff.


## Pushing a new release

1. Roll the version/revision numbers in `mode.properties`

2. Tag the latest and push

        git tag -a rev1279 -m 'Revision 1279 (Processing 4.0b4)'
        git push origin --tags

3. Delete the previous `latest` tag

        git tag -d latest
        git push origin :refs/tags/latest

4. Create new `latest` tag with the current state of the repo

        git tag -f -a latest -m 'Revision 1279 (Processing 4.0b4)'
        git push -f --tags

5. Create the distribution

        ant dist

    Then upload dist/javafx.zip and dist/javafx.txt to the `latest` tag on Github. Can also upload them to the tag for the current version, for anyone installing manually.

6. Add changes in MarkDown format to the release: <https://github.com/processing4/processing4-javafx/releases>

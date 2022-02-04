# Revision 1280 (for Processing 4.0 beta 5)

*3 February 2022*

* Fixes for the folder layout (that were manually added while the previous release was being posted).

* Updating handlers and functions for moving and resizing windows. [\#53](https://github.com/processing/processing4/issues/53)


# Revision 1279 (for Processing 4.0 beta 4)

*23 January 2022*

The JavaFX binaries have grown very large in size so it was necessary to move JavaFX to its own library. This avoids making the Processing download excessively large, given that not everyone uses JavaFX. More discussion/explanation [here](https://github.com/processing/processing4/issues/348).


## Changes

* For Processing 4.0 beta 4, now a separate library to be installed from the Contributions Manager.

* Now building for our six base platforms described [here](https://github.com/processing/processing4/wiki/Supported-Platforms).

* An internet connection is necessary for the build, because it checks the downloads. (Otherwise the build script is more complicated than necessary to see if all six files are available.)


## Fixes

+ Make offscreen `PGraphicsFX2D` work, a patch from @GKFX. [#4638](https://github.com/processing/processing/issues/4638), [#4698](https://github.com/processing/processing/pull/4698)

# CLImage

Convert images to beautiful ANSI escape codes for display in commandline interfaces.

Available as both a CLI application and a Python library.

![demo](https://raw.github.com/pnappa/CLImage/master/extra/demo.png)

# TODO:
    - write docstrings
    - investigate different scaling modes? 256 color sometimes looks better for colors (than truecolor)?
    - rename the `_toAnsi` fn, as it's not really right (ANSI is restricted to the 16 color stuff, right?)
    - add a detect option to --palette, to automatically detect mapping of system colors? this might be hard.
    - run the fabled pylint on the codebase
    - Python library section link in setup.py, and in this README

# Features
 - Custom sized images
 - ASCII or Unicode support
    - Unicode enables 4x more detail
 - 8/16/256/Truecolor support, for a wider gamut of colors
 - Selectable system palettes to adjust for user terminal themes
 - Fast color lookup with KDTrees & memoization

# Usage

CLImage is available as both a standalone CLI program, or available for import as a Python3 library.

## CLI Program

By default converting an image will output in 256 color, as 80 columns, and ASCII (for reasonable compatibility).
```bash
$ climage image.png
```
![demo](https://raw.github.com/pnappa/CLImage/master/extra/warhol256ascii.png)


A nicer image can be obtained when enabling unicode and truecolor flags.
```bash
$ climage --unicode --truecolour image.png
```
![demo](https://raw.github.com/pnappa/CLImage/master/extra/warholtruecolorunicode.png)

For display in TTYs such as the Linux terminal before starting X11 (also accessible by Ctrl-Alt-F3, etc), you should restrict yourself to 8 color, and ASCII only. As 8 and 16 colors are solely constructed out of system colors (often set by the terminal theme), it is recommended to select a palette for these, depending on what you have selected.
```bash
$ climage --8color warholcropped.png --palette solarized
```
![demo](https://raw.github.com/pnappa/CLImage/master/extra/warhol8colsolarized.png)

Further options may be found by running `climage --help`

## Python Library

Detail:
    - some `to_file` fn? outputs the image to file
    - some simple `convert` fn, that returns a string of the image

```python3
import climage
```
*TODO: actually decide m8*



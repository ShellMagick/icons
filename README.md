# ShellMagick icons collection

## Generic notes

- _dark_ and _light_ do not refer to in which mode the icons "should be used", but rather the generic tone of the icons themselves
    - thus _dark_ is usually the one to be used in light mode
    - thus _light_ is usually the one the be used in dark mode
- `inkscape` refers to the [InkScape CLI](https://inkscape.org/doc/inkscape-man.html)

### Notes about self-created logos

#### `shellmagick-(dark|light).svg`

I have created these with the following, non-deterministic steps:

1. Generated a bunch of logos for the string "ShellMagick" with https://www.freelogodesign.org/
2. Looked around until I have found something that I liked
    - Celtic themed, check
    - Shell-ish, check
    - ⇒ This was the basic geometry of the logo
3. Downloaded the picture
4. Opened it in GIMP
5. Created a monocrome version of it
6. Tidied it up (removed the watermark, etc.)
7. Uploaded it to https://www.freeconvert.com/
8. Downloaded it as SVG
9. Colorized it with InkScape
    - The colors are from Tinted Theming: [Everforest](https://tinted-theming.github.io/base16-gallery/), created by [Sainnhe Park](https://github.com/sainnhe)
    - I just picked 3 colors which worked for me for a _light_ and _dark_ version of the created logo

## The icons

### In the folder `icons/src`

#### Downloaded "sources"

| Picture | Source | License |
|---------|--------|--------:|
| `cmd-dark.svg`               | [SVG Repo](https://www.svgrepo.com/svg/361366/terminal-cmd)                                                                                      | MIT            |
| `cygwin-dark.svg`            | [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Cygwin_logo.svg)                                                                     | Public domain  |
| `mingw-dark.svg`             | [MinGW website](https://www.mingw-w64.org/) (Light mode)                                                                                         | Public domain? |
| `mingw-light.svg`            | [MinGW website](https://www.mingw-w64.org/) (Dark mode)                                                                                          | Public domain? |
| `powershell-dark.svg`        | [SVG Repo](https://www.svgrepo.com/svg/473762/powershell)                                                                                        | Logo License¹  |
| `powershell-light.svg`       | [SVG Repo](https://www.svgrepo.com/svg/373992/powershell)                                                                                        | MIT            |
| `shellmagick-dark.svg`       | See description                                                                                                                                  | MIT            |
| `shellmagick-light.svg`      | See description                                                                                                                                  | MIT            |
| `tux.svg`                    | [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Tux.svg)                                                                             | CC0-BY²        |
| `windows-terminal-dark.svg`  | [GitHub repository](https://github.com/microsoft/terminal/blob/4e7b63c664bc09da3ba2f08287cf03d3729ce3a2/res/terminal/Terminal.svg?plain=1#L4)    | MIT            |
| `windows-terminal-light.svg` | [GitHub repository](https://github.com/microsoft/terminal/blob/4e7b63c664bc09da3ba2f08287cf03d3729ce3a2/res/terminal/Terminal_HC.svg?plain=1#L4) | MIT            |

#### Processed "sources"

| Picture | Source | Modifications |
|---------|--------|:--------------|
| `cmd-light.png`         | `cmd-dark.svg`          | Inverted the colors manually with InkScape, made the background black |
| `cygwin-light.svg`      | `cygwin-dark.svg`       | Inverted the colors manually with InkScape, made the background black |

¹ I sincerly disregard this license and handle the source file as if it were MIT-licensed, based on the fact that it in itself is a remix of `powershell-light.svg`
² By [lewing@isc.tamu.edu Larry Ewing](mailto:lewing@isc.tamu.edu) and [The GIMP](https://en.wikipedia.org/wiki/GIMP)

## Icons

Each folder defines the dimensions of the exported PNG files.

| Picture                      | Obtained by (example command for  `32x32`)                                                                                             |
|------------------------------|:----------------------------------------------------------------------------------------------------------------------|
| `cmd-dark.png`               | `inkscape -w 32 -h 32                           ./src/cmd-dark.svg               -o ./32x32/cmd-dark.png              ` |
| `cmd-light.png`              | `inkscape -w 32 -h 32                           ./src/cmd-light.svg              -o ./32x32/cmd-light.png             ` |
| `cygwin-dark.png`            | `inkscape -w 32 -h 32                           ./src/cygwin-dark.svg            -o ./32x32/cygwin-dark.png           ` |
| `cygwin-light.png`           | `inkscape -w 32 -h 32                           ./src/cygwin-light.svg           -o ./32x32/cygwin-light.png          ` |
| `mingw-dark.png`             | `inkscape -w 32 -h 32 --export-area=0:0:117:117 ./src/mingw-dark.svg             -o ./32x32/mingw-dark.png            ` |
| `mingw-light.png`            | `inkscape -w 32 -h 32 --export-area=0:0:117:117 ./src/mingw-light.svg            -o ./32x32/mingw-light.png           ` |
| `powershell-dark.png`        | `inkscape -w 32 -h 32                           ./src/powershell-dark.svg        -o ./32x32/powershell-dark.png       ` |
| `powershell-light.png`       | `inkscape -w 32 -h 32                           ./src/powershell-light.svg       -o ./32x32/powershell-light.png      ` |
| `shellmagick-dark.png`       | `inkscape -w 32 -h 32                           ./src/shellmagick-dark.svg       -o ./32x32/shellmagick-dark.png      ` |
| `shellmagick-light.png`      | `inkscape -w 32 -h 32                           ./src/shellmagick-light.svg      -o ./32x32/shellmagick-light.png     ` |
| `tux.png`                    | `inkscape -w 32 -h 32                           ./src/tux.svg                    -o ./32x32/tux.png                   ` |
| `windows-terminal-dark.png`  | `inkscape -w 32 -h 32                           ./src/windows-terminal-dark.svg  -o ./32x32/windows-terminal-dark.png ` |
| `windows-terminal-light.png` | `inkscape -w 32 -h 32                           ./src/windows-terminal-light.svg -o ./32x32/windows-terminal-light.png` |

Of course, this can be done iteratively, e.g., by executing the following in Windows CMD:
```cmd
for %d in (8, 16, 32, 64, 128, 256) do (
    mkdir .\%dx%d
    for /R %f in (.\src\*.svg) do (
        inkscape -w %d -h %d %f -o .\%dx%d\%~nf.png
    )
    for /R %f in (.\src\mingw*.svg) do (
        inkscape -w %d -h %d --export-area=0:0:117:117 %f -o .\%dx%d\%~nf.png
    )
)
```

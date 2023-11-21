# Video-Slideshow

Creation of a video file from metadata of image files and their graphical content.

## Requirement

The shell script to use requires the programs [“ImageMagick”](https://imagemagick.org/) and [“FFmpeg”](https://ffmpeg.org/) to be installed.

## Installation

* Download [create_slideshow](./src/create_slideshow).
* Make sure the `create_slideshow` file is executable:
  ```
  chmod u+x create_slideshow
  ```
* Move `create_slideshow` to a location included in the `PATH` environment variable (e.g. `$HOME/bin`, `/usr/local/bin`, ...)

## Application

Call `create_slideshow` in a directory that contains the desired image files. A video file is then created (format “mp4”), which consists of a combination of the text of the metadata “Caption/Abstract” (`IPTC:2:120`) and “DateTimeOriginal” (`EXIF`) as well as the graphical content.

## Modifications

By changing the constants `VIDEO_FILE`, `RESOLUTION` and `DELAY` inside the script, the result can be adapted to your own requirements.

# Video Slideshow

Creation of a video file from metadata of image files and their graphical content.

## Requirement

The shell script to use requires the programs “[ImageMagick](https://imagemagick.org/)” and “[FFmpeg](https://ffmpeg.org/)” to be installed.

## Installation

* Download [create_slideshow](./src/create_slideshow)

* Make sure the file `create_slideshow` is executable:

  ```
  chmod u+x create_slideshow
  ```
  
* Move `create_slideshow` to a location included in the `PATH` environment variable (e.g. `$HOME/bin`, `/usr/local/bin`, ...)

## Usage

Call 

```
create_slideshow -c -d
```

in a directory that contains the desired image files. A video file is then created (format “mp4”), which consists of a combination of the text of the metadata “Caption/Abstract” (`IPTC:2:120`) and “DateTimeOriginal” (`EXIF`) as well as the graphical content. Command line switches:

```
-c     shows caption
-d     shows date+time
-r #   maximum number of subdirectories (default: #=0)
-V     output version information and exit
-h     help
```

## Modifications

By changing the constants `VIDEO_FILE`, `RESOLUTION` and `DELAY` inside the script, the result can be adapted to your own requirements.

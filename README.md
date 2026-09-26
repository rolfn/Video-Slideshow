# Video Slideshow

Creation of a video file from metadata of image files and their graphical content.

## Requirement

The shell script to use requires the programs “[ImageMagick](https://imagemagick.org/)” and “[FFmpeg](https://ffmpeg.org/)” to be installed.

## Installation

* Download [create_slideshow](./src/create_slideshow)

* Make sure the file `create_slideshow` is executable:

  ```
  chmod +x create_slideshow
  ```
  
* Move `create_slideshow` to a location included in the `PATH` environment variable (e.g. `$HOME/bin`, `/usr/local/bin`, ...)

## Usage

Call 

```
create_slideshow -c -d
```

in a directory that contains the desired image files. A video file is then created (format “mp4”), which consists of a combination of the image metadata and the graphical content. 

During execution, the script outputs the processed titles, intertitles, and captions directly to the terminal, allowing you to easily spot typos before the video rendering begins.

### Metadata handling

* **Caption:** When using the `-c` switch, the script reads the image description primarily from **XMP metadata** (`[XMP:Description]`). If no XMP description is found, it automatically falls back to **IPTC metadata** (`[IPTC:2:120]`).
* **Date and Time:** When using the `-d` switch, the creation date is retrieved from the standard **EXIF metadata** (`[EXIF:DateTimeOriginal]`).

### Command line switches:


```
-c     shows caption (prefers XMP, falls back to IPTC)
-d     shows date+time
-r #   maximum number of subdirectories (default: #=1)
-V     output version information and exit
-h     help
```

If the text file `title.txt` exists in the top-level directory, the text it contains will be inserted as a main title page at the very beginning.

If a text file named `xxx-intertitle.txt` exists for an image file `xxx.jpg` (or `xxx.png`, etc.), the text it contains will be inserted as a intertitle page before the image-specific text and the image itself.

## Modifications

By changing the constants `VIDEO_FILE`, `RESOLUTION`, `DELAY`, and font colors/sizes inside the script, the result can be adapted to your own requirements.

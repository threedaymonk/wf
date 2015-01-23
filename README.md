# wf

A shell-based digital camera workflow.

## What it does

1. Imports new files from your digital media into directories per day
   (YYYY-MM-DD, of course)
2. Generates preview images (max 1024 pixels) for easy reviewing

Image processing is performed in parallel to speed things up.

## Dependencies

* ImageMagick
* exiv2
* ufraw-batch
* GNU parallel
* ffmpeg

## Supported input types

The extension type is limited to those below, and case is significant.

* JPEG (.JPG)
* QuickTime (.MOV)
* Nikon raw (.NEF)

It should be straightforward to add support for other raw formats supported by
ufraw and for any video format supported by ffmpeg.

## Limitations

* Only Nikon raw files supported
* Some Linux-specific code (e.g. calculating number of processors)

## Paths and configuration

* Original files go in `$WORKFLOW_DIR/original/YYYY-MM-DD/`.
* Preview files go in `$WORKFLOW_DIR/previews/YYYY-MM-DD/`.
* `$WORKFLOW_DIR` defaults to `~/Pictures/Workflow`.
* Mounted media will be hunted in `$MEDIA_DIRS`, which is `/mnt:/media` by
  default.

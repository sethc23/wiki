# Doc Analysis
---

```bash
# Make B&W
convert -normalize -threshold 50% -brightness-contrast 0x10 in.JPG 1blackwhite.pbm

```

### GUI
- [Paperwork](https://github.com/jflesch/paperwork)
- 
identify [-verbose]
`jpegtopnm`
  - "JPEG" a.k.a. "JFIF"
  - using `-comments` prints any comments to stderr
  - use `-exif=-` to print EXIF header to stdout (no image output)
  - OUTPUT format: 
    - PGM (Portable Graymap) [if INPUT is grayscale]
    - PPM (Portable Pixmap) [if INPUT is NOT grayscale]
    - either one byte or two bytes per sample depending on whether the JFIF input has either 8 bits or 12 bits per sample.
      - use `pnmdepth` for two-byte-per-sample --> one-byte-per-sample file if you need to.
  - 
    OUTPUT )=='PGM'
  -else: type(OUTPUT)=='PPM'
  -dumpexif
`wrjpgcom` - add comment to jpeg header

`ppmdither`
`pnmdepth` - one-byte-per-sample file most likely for raw PNM files pre-April 2000
`cjpeg` - convert PPM,PGM,BMP,Targa,RLE to JPEG
pgm (
`jpegtran`
`pgmtopbm`
  - Reads a portable graymap as input.  Produces a portable bitmap as output.
`pgmhist`
pbm
`pgmtofits`
`pnmscale`
`pnmtops`
`pbmreduce`
`pnmconvol`
pnmscale -xysize 2400 3000 image.pgm | pgmtopbm -hil | pnmtops -scale 0.25 > image.ps

test_orig.jpg : 1.7M
test_pnm.ppm : 46M
test_pnm_conv.pbm : 1.9M

```bash


jpegtopnm \
  /home/ub2/ARCHIVE/DOC_IMAGES/test_orig.jpg \
  > /home/ub2/ARCHIVE/DOC_IMAGES/test_pnm.ppm
  
ppmtopgm \
  /home/ub2/ARCHIVE/DOC_IMAGES/test_pnm.ppm|pgmtopbm \
  > /home/ub2/ARCHIVE/DOC_IMAGES/test_pnm_conv.pbm
  
convert -deskew 40% test_pnm_conv_morphed.jpg \
  jpegtopnm - | pnmtotiff - | \
  tesseract - - pdf|pdftotext -layout - -
  
  /home/ub2/ARCHIVE/DOC_IMAGES/test_pnm_conv_morphed_deskewed.tiff
  
```

[User Notes for C-Tesseract](http://stackoverflow.com/questions/30688840/access-confidence-in-python-tesseract)

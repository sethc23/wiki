# Doc Analysis
---

```bash
# Make B&W
convert -normalize -threshold 50% -brightness-contrast 0x10 in.JPG 1blackwhite.pbm

```

### GUIs:
- [Paperwork](https://github.com/jflesch/paperwork)
- [Terese: A Tesseract Correction Tool](http://terese.sourceforge.net/)
 
### Command Line:
- `identify [-verbose]`
  - obtain detailed information and calculations (careful with verbose)


- `jpegtopnm`
  - "JPEG" a.k.a. "JFIF"
  - `-comments` prints any comments to stderr
  - `-exif=-` prints EXIF header to stdout (no image output)
  - `dumpexif`
  - OUTPUT format: 
    - PGM (Portable Graymap) [if INPUT is grayscale]
    - PPM (Portable Pixmap) [if INPUT is NOT grayscale]
    - either one byte or two bytes per sample depending on whether the JFIF input has either 8 bits or 12 bits per sample.
      - use `pnmdepth` for two-byte-per-sample --> one-byte-per-sample file if you need to.


- `wrjpgcom` - add comment to jpeg header


- `ppmdither`


- `pnmdepth` - one-byte-per-sample file most likely for raw PNM files pre-April 2000


- `cjpeg` - convert PPM,PGM,BMP,Targa,RLE to JPEG


- `jpegtran`


- `pgmtopbm` - Reads a portable graymap as input.  Produces a portable bitmap as output.


- `pgmhist`


- `pgmtofits`


- `pnmscale`


- `pnmtops`

- `pbmreduce`

- `pnmconvol`



  > **EXAMPLES**:

    ```bash
    pnmscale -xysize 2400 3000 image.pgm | pgmtopbm -hil | pnmtops -scale 0.25 > image.ps

    jpegtopnm \
      /home/ub2/ARCHIVE/DOC_IMAGES/test_orig.jpg \
      > /home/ub2/ARCHIVE/DOC_IMAGES/test_pnm.ppm
      
    ppmtopgm \
      /home/ub2/ARCHIVE/DOC_IMAGES/test_pnm.ppm|pgmtopbm \
      > /home/ub2/ARCHIVE/DOC_IMAGES/test_pnm_conv.pbm
      
    convert -deskew 40% test_pnm_conv_morphed.jpg \
      jpegtopnm - | pnmtotiff - | \
      tesseract - - pdf|pdftotext -layout - -
      
    ```

- [Tesseract: API Examples](https://github.com/tesseract-ocr/tesseract/wiki/APIExample)
- [Teseract: C-API Reference (v. 4.0)](https://tesseract-ocr.github.io/a00638.html#af05c5f7be48946d521660f05323417e7)
- [Teseract: C-API Reference (v. 3.0)](http://tess4j.sourceforge.net/docs/docs-3.0/net/sourceforge/tess4j/TessAPI1.html)
- [Leptonica: C-API Reference](http://tpgit.github.io/UnOfficialLeptDocs/leptonica/functions.html)
- [User Notes for C-Tesseract](http://stackoverflow.com/questions/30688840/access-confidence-in-python-tesseract)
- [OpenCV Examples](http://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials)
- [Doc Scanner In A Day Example](http://www.pyimagesearch.com/2014/09/01/build-kick-ass-mobile-document-scanner-just-5-minutes/)
- [Pt2](http://www.pyimagesearch.com/2014/08/25/4-point-opencv-getperspective-transform-example/)

- [ImageMagick: Positional Arg Clarity](http://www.imagemagick.org/discourse-server/viewtopic.php?t=18241)
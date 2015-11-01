FFmpeg README
=============

FFmpeg is a collection of libraries and tools to process multimedia content
such as audio, video, subtitles and related metadata.

## Libraries

* `libavcodec` provides implementation of a wider range of codecs.
* `libavformat` implements streaming protocols, container formats and basic I/O access.
* `libavutil` includes hashers, decompressors and miscellaneous utility functions.
* `libavfilter` provides a mean to alter decoded Audio and Video through chain of filters.
* `libavdevice` provides an abstraction to access capture and playback devices.
* `libswresample` implements audio mixing and resampling routines.
* `libswscale` implements color conversion and scaling routines.

## Tools

* [ffmpeg](http://ffmpeg.org/ffmpeg.html) is a command line toolbox to
  manipulate, convert and stream multimedia content.
* [ffplay](http://ffmpeg.org/ffplay.html) is a minimalistic multimedia player.
* [ffprobe](http://ffmpeg.org/ffprobe.html) is a simple analisys tool to inspect
  multimedia content.
* Additional small tools such as `aviocat`, `ismindex` and `qt-faststart`.

## Compilation
Set following variables: 
* PREFIX
* TOOLCHAIN
* SYSROOT
* ADDI_CFLAGS
* FREETYPE_INC_DIR
* FREI0R_INC_DIR
* LIBVPX_INC_DIR
* ADDI_LDFLAGS
* FREETYPE_OUTPUT_DIR
* LIBVPX_OUTPUT_DIR
* ADDITIONAL_CONFIGURE_FLAG

Then call "configure".
Example: 

    configure \
    --prefix=$PREFIX \
    --enable-shared \
    --enable-libfreetype \
    --enable-libvpx \
    --disable-doc \
    --disable-ffmpeg \
    --disable-ffplay \
    --disable-ffprobe \
    --disable-ffserver \
    --disable-avdevice \
    --disable-doc \
    --disable-symver \
    --cross-prefix=$TOOLCHAIN/bin/arm-linux-androideabi- \
    --target-os=linux \
    --arch=arm \
    --enable-cross-compile \
    --sysroot=$SYSROOT \
    --extra-cflags="-Os -fpic $ADDI_CFLAGS -I$FREETYPE_INC_DIR -I$FREI0R_INC_DIR -I$LIBVPX_INC_DIR" \
    --extra-ldflags=$ADDI_LDFLAGS \
    --extra-libs="-L${FREETYPE_OUTPUT_DIR}/lib/ -lfreetype2 -L${LIBVPX_OUTPUT_DIR}/lib/"
    $ADDITIONAL_CONFIGURE_FLAG
  
  Then start compilation using "make install" command

## Documentation

The offline documentation is available in the **doc/** directory.

The online documentation is available in the main [website](http://ffmpeg.org)
and in the [wiki](http://trac.ffmpeg.org).

### Examples

Coding examples are available in the **doc/examples** directory.

## License

FFmpeg codebase is mainly LGPL-licensed with optional components licensed under
GPL. Please refer to the LICENSE file for detailed information.

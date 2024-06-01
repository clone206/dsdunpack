# DSD Unpack

20240601: Added support for sending raw DSD to stdout.

This utility converts DSD audio between Sony DSF (.dsf) and Philips DSDIFF
(.dff) container formats, including decompression of DST-encoded DSDIFF files
and ID3 tags in both containers.

Parts of this project are based on the SACD Ripper project, particularly
libsacd and libdstdec. See https://sacd-ripper.github.io/ for more info.

Tested on Ubuntu with gcc. You will need
pthreads-win32 to build using MSVC.

## Building
```
cmake -B build -S .
cmake --build build
```

## Usage

`./build/dsdunpack --help`:

```
dsdunpack [options] inputfile outputfile
  -p, --output-dsdiff             : output as Philips DSDIFF (.dff) file
  -s, --output-dsf                : output as Sony DSF (.dsf) file
  -o, --output-stdout             : output raw Interleaved MSBF DSD to stdout
  -t, --ignore-tags               : ignore (do not copy) ID3 tags
  -v, --verbose                   : print file info and progress
  inputfile                       : source file
  outputfile                      : target file
 If no output format is specified, it is detected from output file name.

Help options:
  -?, --help                      : Show this help message
  --usage                         : Display brief usage message
```
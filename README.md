# inspectrum
inspectrum is a tool for analysing captured signals, primarily from software-defined radio receivers.

![inspectrum screenshot](/screenshot.jpg)

## Features
 * Large (100GB+) file support
 * Spectrogram with zoom/pan
 * Vertical zoom for detailed frequency inspection
 * Plots of amplitude, frequency, phase and IQ samples
 * Cursors for measuring period, symbol rate and extracting symbols
 * Export of selected time period, filtered samples and demodulated data

## Install
### Linux
Install inspectrum with your package manager, it should be present in most distros.

### macOS
 * [Homebrew](https://formulae.brew.sh/formula/inspectrum)
 * [MacPorts](https://ports.macports.org/port/inspectrum/)

## Windows
 * [radioconda](https://github.com/ryanvolz/radioconda)
 * [conda](https://anaconda.org/conda-forge/inspectrum)

## Build from source
### Prerequisites

 * cmake >= 3.1
 * fftw 3.x
 * [liquid-dsp](https://github.com/jgaeddert/liquid-dsp) >= v1.3.0
 * pkg-config
 * qt5

### Build instructions

Build instructions can be found here: https://github.com/miek/inspectrum/wiki/Build

### Run

    ./inspectrum [filename]

## Input
inspectrum supports the following file types:
 * `*.sigmf-meta, *.sigmf-data` - SigMF recordings
 * `*.cf32`, `*.fc32`, `*.cfile` - Complex 32-bit floating point samples (GNU Radio, osmocom_fft)
 * `*.cf64`, `*.fc64` - Complex 64-bit floating point samples
 * `*.cs32`, `*.sc32`, `*.c32` - Complex 32-bit signed integer samples (SDRAngel)
 * `*.cs16`, `*.sc16`, `*.c16` - Complex 16-bit signed integer samples (BladeRF)
 * `*.cs8`, `*.sc8`, `*.c8` - Complex 8-bit signed integer samples (HackRF)
 * `*.cu8`, `*.uc8` - Complex 8-bit unsigned integer samples (RTL-SDR)
 * `*.f32` - Real 32-bit floating point samples
 * `*.f64` - Real 64-bit floating point samples (MATLAB)
 * `*.s16` - Real 16-bit signed integer samples
 * `*.s8` - Real 8-bit signed integer samples
 * `*.u8` - Real 8-bit unsigned integer samples

If an unknown file extension is loaded, inspectrum will default to `*.cf32`.

Note: 64-bit samples will be truncated to 32-bit before processing, as inspectrum only supports 32-bit internally.

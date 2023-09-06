# VBAP package for Max
[![Build Status](https://travis-ci.org/nwolek/vbap.svg?branch=master)](https://travis-ci.org/nwolek/vbap)
[![Build status](https://ci.appveyor.com/api/projects/status/vn5l7cmal244ti57?svg=true)](https://ci.appveyor.com/project/nwolek/vbap)


Legacy objects for Vector Based Amplitude Panning in Max authored by [Ville Pullki](https://people.aalto.fi/index.html#ville_pulkki), adapted by [Nathan Wolek](https://github.com/nwolek) and modified for Max 8 by [Shakeeb Alireza](https://github/shakfu)

## About

This GitHub project is a [package for Cycling74's Max](https://cycling74.com), versions 8.5 or higher. It provides newly compiled, 64-bit versions of Ville Pullki's objects for vector-based amplitude panning that were originally developed in 1998.

Vector-based amplitude panning is a technique for spatializing sound across multiple loudspeakers. It is flexible enough to define an arbitrary number of speakers in 2D or 3D space. After speaker positions are defined, the user can move a single sound source through the configuration by adjusting its apparent azimuth and elevation.

Additional resources:

- [AES paper on VBAP](http://lib.tkk.fi/Diss/2001/isbn9512255324/article1.pdf) by Ville Pullki, published originally in 1997 by Journal of the Audio Engineering Society  

- [Legacy website for research group](http://legacy.spa.aalto.fi/research/cat/vbap/) at Helsinki University of Technology  

- Distinct implementation of [VBAP for PD](https://github.com/pierreguillot/vbap) by Pierre Guillot of CICM  

- [3D Sound Primer](http://www.garykendall.net/papers/3-DPrimer1995.pdf) by Gary Kendall, published originally in 1995 by Computer Music Journal 

## Installing

If you have [Git](http://git-scm.com/) installed, you can install via the Terminal using the following commands for Max 8:

```bash
cd ~/Documents/Max\ 8/Packages
git clone https://github.com/nwolek/vbap.git
cd vbap
./build_macos_.sh # quick build for macos
```

see the `How to Build` section below for detailed build instructions for windows and macos.

If you do not have Git installed, you can [download the latest release here](https://github.com/nwolek/vbap/releases). After decompressing the zip archive, the resulting folder can be placed in one of the following folders:

* `~/Documents/Max\ 8/Packages`

## How To Build

The build system for this project is based on the [max-sdk](https://github.com/Cycling74/max-sdk) and the [max-sdk-base](https://github.com/cycling74/max-sdk-base).


### Prerequisites

To build the externals in this package you will need some form of compiler support on your system. 

* On the Mac this means Xcode (you can get from the App Store for free). 
* On Windows this most likely means some version of Visual Studio (the free versions should work fine).

You will also need to install [CMake](https://cmake.org/download/).


### Building

0. Get the code from Github, or download a zip and unpack it into a folder.
1. In the Terminal or Console app of your choice, change directories (cd) into that folder.
2. `mkdir build` to create a folder with your various build files
3. `cd build` to put yourself into that folder
4. Now you can generate the projects for your choosen build environment:

#### Mac 

You can build on the command line using Makefiles, or you can generate an Xcode project and use the GUI to build.

* Xcode: Run `cmake -G Xcode ..` and then open the Xcode project from this "build" folder.
* Terminal: Run `cmake -G Xcode ..` and then run `cmake --build . --config Release`

#### Windows

The exact command line you use will depend on what version of Visual Studio you have installed.  You can run `cmake --help` to get a list of the options available.  Assuming some version of Visual Studio 2013, the commands to generate the projects will look like this:

* 32 bit: `cmake -G "Visual Studio 12" ..`
* 64 bit: `cmake -G "Visual Studio 12 Win64" -DWIN64:Bool=True ..`

Having generated the projects, you can now build by opening the .sln file in the build folder with the Visual Studio app (just double-click the .sln file) or you can build on the command line like this:

`cmake --build . --config Release`


## Bug reporting

If you feel that you have found a bug, please report it via [the Issues section](https://github.com/nwolek/vbap/issues) of this GitHub project site.

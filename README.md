# wolfnlf

An experimental Windows version of binarizewolfjolion program.

## Background

Original code from the 
https://github.com/liris-vision/modules/tree/master/BinarizeWolfJolion 

which originates from article http://liris.cnrs.fr/christian.wolf/publications/index.html#icpr2002v
and source code  http://liris.cnrs.fr/christian.wolf/software/binarize/index.html


## Changes

This version utilizes the DLL version of liris-vision/modules, and adds command-line options in style
of the original program for utilization in windows environment.

The compilation has been done with Visual Studio 2015, so needed solution files are included.

## Prerequisites

Compilation requires opencv 2.3.1 (as liris-vision version, at the moment). The property file contain
a library directories and library files , but change the paths according to settings in given environment.

## TODO & :warning: 

Plenty. 
* Command-line handling is bit kludgy, some incorrect stuff can crash the program
* opencv version could be upgraded to a newer one from 2.3.1 
* parameter handling in process method
etc.


# Compilation

Once you have setup opencv

1. Open the wolfnlf.sln in Visual Studio
2. Pick Release, x64 and build solution

You should get to a X64\Release directory executable called 'wolfnlf.exe'

In case of issues check property files, that opencv directories and libraries are correct.


## Usage

By default the program uses 'Wolf et al.' as default binarization algorithm

In its simplest case, program requires just input file and name of output file:

x64\Release\wolfnlf.exe w x64\Release\sadekone.pgm sadekone_out.pgm 


### Full usage

```
usage: x64\Release\wolfnlf.exe [ /x:<winx> /y:<winy> /k:<parameter> ] [ version ] <inputimage> <outputimage>

version: n   Niblack (1986)         needs white text on black background
         s   Sauvola et al. (1997)  needs black text on white background
         w   Wolf et al. (2001)     needs black text on white background

Default version: w (Wolf et al. 2001)

example:
       x64\Release\wolfnlf.exe w in.pgm out.pgm
       x64\Release\wolfnlf.exe in.pgm out.pgm
       x64\Release\wolfnlf.exe /x:50 /y:50 /k:0.6 in.pgm out.pgm

```




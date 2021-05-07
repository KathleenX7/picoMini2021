# advanced-potion-making

## Overview

Category: Forensics

Author: bigC

100 points

## Description

Ron just found his own copy of advanced potion making, but its been corrupted by some kind of spell. Help him recover it!

### Challenge Endpoints

| | |
|-|-|
|Download advanced-potion-making|[advanced-potion-making](./advanced-potion-making)|

## Approach

Open the file in [HxD](https://mh-nexus.de/en/hxd/) or any [hex editor](https://en.wikipedia.org/wiki/Hex_editor). This seems to be a [PNG file](https://fileinfo.com/extension/png) based on the [IHDR](http://www.libpng.org/pub/png/spec/1.2/PNG-Chunks.html)

Some things before the IHDR tag were incorrect so I compared it against a viable PNG.

Change `89 50 42 11 0D 0A 1A 0A 00 12 13 14 49` to `89 50 4E 47 0D 0A 1A 0A 00 00 00 0D` and it becomes a valid PNG file. The entire file is red:

![advanced-potion-making.png](./advanced-potion-making.png)

Using our trusty friend [stegsolve](https://github.com/eugenekolo/sec-tools/tree/master/stego/stegsolve/stegsolve) we can see the flag is hidden in `Red plane 0`

![flag](./solved.bmp)

## Flag

picoCTF{w1z4rdry}

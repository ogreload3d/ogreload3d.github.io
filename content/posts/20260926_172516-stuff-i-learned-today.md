+++
author = 'ogreload3d'
date = '2026-09-26T17:25:17+09:00'
draft = false
title = '20260926_172516 Stuff I Learned Today'
tags = []
title-images = []
ending-images = []
table-of-contents = true
toc-auto-numbering = true
+++

## A big day for Programming!

Anyway I can't believe I finally set up my own "bare metal" system here! It took me forever to just set up all the files, get all the alises etc. but man, we really did it.

I'll put up some stuff I learned today, such as

## How to set up your hugo to instantly post!!

```bash
alias hugopost='f() { hugo new posts/$(date +%Y%m%d_%H%M%S)-$1.md; }; f'
```

this will allow you to create a post mega quick by just going like "hugopost my-cool-post" and it'll just do the rest. Amazing!

## neopost github is great, but you needa understand what's going on

Then what else I found: [the neopost github repo is real good](https://github.com/salatine/neopost), but the `basic_info.md` is wrongly named in the sidebar folder. it should be `basic-info.md` !

There are a bunch of other problems with that repo as well, such as you need to have a posts.md archetype. Plus it's like using the YAML settings while files are in TOML etc. It's kinda nuts, if I feel like it, I'll maybe open a PR but not day lol it's been a day.

## imagemagick ROCKS

Also I got a new PFP here. Imagemagick came in CRACKED yo with all the dithering. In order to install imagemagick in WSL it was a bit bullshit:

```bash
echo "=== 1. Updating system and installing dependencies ==="
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential pkg-config libtool git \
  libwebp-dev libheif-dev libde265-dev libx265-dev \
  libjpeg-dev libpng-dev libtiff-dev libopenjp2-7-dev \
  libdjvulibre-dev libwmf-dev libraw-dev libjxl-dev \
  libfreetype6-dev libfontconfig1-dev libxml2-dev \
  libgs-dev liblqr-1-0-dev libglib2.0-dev libgomp1

echo "=== 2. Cloning ImageMagick source code ==="
cd ~/
if [ -d "ImageMagick" ]; then
    rm -rf ImageMagick
fi
git clone https://github.com/ImageMagick/ImageMagick.git
cd ImageMagick

echo "=== 3. Configuring the build with full feature modules ==="
./configure --with-modules --with-gomp --with-lqr --with-security-policy=open

echo "=== 4. Compiling and installing (using all CPU cores) ==="
make -j$(nproc)
sudo make install
sudo ldconfig

echo "=== 5. Verification ==="
magick -version
```

cuz apparently you need to get """dependencies""" and """delegates""" installed properly BEFORE even thinking about getting imagemagick

But then you can do shit like

```bash
magick pfp2.png -resize 500x500\> -ordered-dither o4x4 -level 10%,70% -colors 16 pfp3.gif
```
and it'll crunch up your files REAL good. If I find any cool crunchers I'll do it more.

Anyway I hope you enjoyed this cool post! Did a whole bunch of coding instead of browsing Reddit or 4chan like a dweeb!
Plus this is like the longest I have written before I let AI take the wheel. Man, work SUCKS but thank god machines will do it all FOR me so I can STAY IN MEETINGS more!
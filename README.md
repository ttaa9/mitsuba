
This is just to tie me over until `mitsuba2` has a GUI.

This (below) worked with Amy Spark's `hacktoberfest-linux-again` branch.
However, it had issues reading in my XMLs via `mtsgui`.
This seems to have been fixed by merging in subsequent updates from the main github's master branch.

Go to one of these repos:

https://github.com/mitsuba-renderer/mitsuba

https://github.com/amyspark/mitsuba


### Install on Ubuntu 18.04

Install prerequisites.

```
sudo apt-get install build-essential scons git libpng-dev libjpeg-dev libilmbase-dev libxerces-c-dev libboost-all-dev libopenexr-dev libglewmx-dev libxxf86vm-dev libeigen3-dev libfftw3-dev
```

```
sudo apt-get install libcollada-dom-dev
```

```
sudo apt-get install qt5-default libqt5opengl5-dev libqt5xmlpatterns5-dev
```

Move the config file next.
Now, I've put `config.py` for ubuntu 18.04 here already, so this should be unnecessary, but for reference:

```
cp build/config-linux-gcc.py .
mv config-linux-gcc.py config.py
```

Change `-std=c++11` to `-std=gnu++11` in `config.py`

Attempt to build and compile:

`QT_SELECT=qt5 scons -j4`

You need to run `source setpath.sh` to run `mtsgui` now.

### Issues with Running

It attempts to convert scene xmls from v0.4 to v0.6, despite the xml clearly BEING labelled as 0.6.
This causes a segfault. Sometimes. Seemingly fixed by subsequent merge from main repo.
 

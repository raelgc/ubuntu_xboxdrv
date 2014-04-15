Additional setup for xboxdrv
----------------------------

This package contains additional configuration to make [`xboxdrv`](http://pingus.seul.org/~grumbel/xboxdrv/) get properly configured and running 
under Ubuntu (14.04).

Additionally, a "Joysticks" entry is created into System Settings panel.

# Install

If you want just use this package:

```term
sudo apt-add-repository -y ppa:rael-gc/ubuntu-xboxdrv
sudo apt-get update
sudo apt-get install ubuntu-xbobxdrv
```

# Build Instructions

This is not required to use this package.

Fist clone this repo (dooh).

To build a `.deb` from this repo:

```term
cd ubuntu-xboxdrv-20140415
rm -Rf ../ubuntu-xboxdrv_*
dh_make -s --indep --createorig --yes
debuild -us -uc
```

To build the source package to send to launchpad:

```term
cd ubuntu-xboxdrv-20140415
rm -Rf ../ubuntu-xboxdrv_*
dh_make -s --indep --createorig --yes
debuild -S -sa
```

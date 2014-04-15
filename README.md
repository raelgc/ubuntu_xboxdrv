ubuntu_xboxdrv
==============

Additional setup for xboxdrv under Ubuntu (14.04).

This package creates a proper daemon for xboxdrv in Ubuntu, and add a "Joysticks" entry into System Settings.

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

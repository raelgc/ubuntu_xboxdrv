ubuntu_xboxdrv
==============

Additional setup for xboxdrv under Ubuntu

# Build Instructions

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

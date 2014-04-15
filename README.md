ubuntu_xboxdrv
==============

Additional setup for xboxdrv under Ubuntu

# Build Instructions

To build a .deb from this repo:

```term
rm -Rf ubuntu-xboxdrv_*
cd ubuntu-xboxdrv-20140415
dh_make -s --indep --createorig --yes
debuild -us -uc
```

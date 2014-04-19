Ubuntu xboxdrv Integration
----------------------------

This package will install [`xboxdrv`](http://pingus.seul.org/~grumbel/xboxdrv/) and get it properly configured and running under Ubuntu (14.04).

Over xboxdrv:
- It cleans broken configurations;
- Properly configure a daemon;
- Manage xboxdrv daemon on System suspend/resume;
- Add a "Joysticks" entry into System Settings panel.


## Install

If you want just use this package:

```term
sudo apt-add-repository -y ppa:rael-gc/ubuntu-xboxdrv
sudo apt-get update
sudo apt-get install ubuntu-xbobxdrv
```

## Build Instructions

This is not required to use this package.

These instructions are supposed to debug or compile the package from source.

### 1 - Clone this repo

```term
git clone git@github.com:raelgc/ubuntu_xboxdrv.git
```

### 2 - Enter project and remove old stuff

```term
cd ubuntu-xboxdrv
rm -Rf ../ubuntu-xboxdrv_*
```
### 3 - Create source for the packages

```term
dh_make -s --indep --createorig --yes -p ubuntu-xboxdrv_<version>
```

### 4 - Create `.changes` to send to Launchpad

```term
debuild -S -sa
```

### Troubleshooting

If you want only create a `.deb` file, after follow step 1, 2, 3:

```term
debuild -us -uc
```

If you're trying to build the `.changes` file using the source code from Launchpad with your gpg key, use:

```term
debuild -S -rfakeroot -k<your_gpg_key_id>
```

Ubuntu xboxdrv Integration
----------------------------

While xpad (the included in kernel joystick driver) works accordingly with wired version of X360 controller, [`xboxdrv`](http://pingus.seul.org/~grumbel/xboxdrv/) offers proper support for wireless and XBox One versions.

And unlike the stock xpad kernel driver, xboxdrv provides a wide varity of configuration options: it allows you to simulate keyboard and mouse events, remap buttons and axes, apply autofire, invert axis, tweak axis sensitivity, emulate throttle and rudder controls and send macros.

Additionally, xboxdrv can also be used for other gamepad to mimic x360 gamepad, which is required for some games.

The good news is xboxdrv is included in its last version on Ubuntu 14.04. The bad news: the installed package has only the driver included, with no additional configuration.

This package adds additional configurations over xboxdrv:

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

## Start/stop the job

The `xboxdrv` job is already started when the package is installed. But, if for some reason, you need to restart it, run in terminal:

```term
sudo service xboxdrv restart
```

## Build Instructions

This is not required to use this package.

These instructions are supposed to debug or compile the package from source.

**Step 1** - Clone this repo

```term
git clone git@github.com:raelgc/ubuntu_xboxdrv.git
```

**Step 2** - Enter project and remove old stuff

```term
cd ubuntu-xboxdrv
rm -Rf ../ubuntu-xboxdrv_*
```
**Step 3** - Create source for the packages

```term
dh_make -s --indep --createorig --yes -c gpl3 -p ubuntu-xboxdrv_<version>
```

**Step 4** - Create `.changes` to send to Launchpad

```term
debuild -S -sa
```

## Troubleshooting

If you want only create a `.deb` file, after follow step 1, 2, 3:

```term
debuild -us -uc
```

If you're trying to build the `.changes` file using the source code from Launchpad with your gpg key, use:

```term
debuild -S -rfakeroot -k<your_gpg_key_id>
```

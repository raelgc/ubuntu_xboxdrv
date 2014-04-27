Ubuntu xboxdrv Integration
----------------------------

Unlike stock xpad kernel driver, [`xboxdrv`](http://pingus.seul.org/~grumbel/xboxdrv/) provides a wide variety of configuration options: it allows you to simulate keyboard and mouse events, remap buttons and axes, apply autofire, invert axis, tweak axis sensitivity, emulate throttle and rudder controls and send macros.

But while xboxdrv is included in its last version on Ubuntu 14.04, it lacks additional configuration to get it properly working.

This package adds additional configurations over xboxdrv:

- It cleans broken configurations;
- Properly configure a daemon;
- Manage xboxdrv daemon on System suspend/resume;
- Add support for user options at /etc/default/xboxdrv;
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

This is not required to use this package: these instructions are supposed to debug or compile the package from source.

After clone this repo:

```term
cd src
rm -Rf ../ubuntu-xboxdrv_*
dh_make -s --indep --createorig --yes -c gpl3 -p ubuntu-xboxdrv_<version>
debuild -S -sa
```

## Troubleshooting

If you want only create a `.deb` file, after Build Instructions:

```term
debuild -us -uc
```

If you're trying to build the `.changes` file using the source code from Launchpad with your gpg key, use:

```term
debuild -S -rfakeroot -k<your_gpg_key_id>
```

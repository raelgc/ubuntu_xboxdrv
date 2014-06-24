Ubuntu xboxdrv Integration
----------------------------

Unlike stock xpad kernel driver, [`xboxdrv`](http://pingus.seul.org/~grumbel/xboxdrv/) provides a wide variety of configuration options: it allows you to simulate keyboard and mouse events, remap buttons and axes, apply autofire, invert axis, tweak axis sensitivity, emulate throttle and rudder controls and send macros.

But while xboxdrv is included in its last version on Ubuntu 14.04, it lacks additional configuration to get it properly working.

This package adds additional configurations over xboxdrv:

- Clear broken configurations;
- Properly configure a upstart service;
- Manage xboxdrv service on System suspend/resume;
- Add support for user options at /etc/default/xboxdrv;
- Start with support for 4 joysticks;
- Add a "Joysticks" entry into System Settings panel;
- Easy ForceFeeback activation.


## Install

If you want just use this package:

```term
sudo apt-add-repository -y ppa:rael-gc/ubuntu-xboxdrv
sudo apt-get update
sudo apt-get install ubuntu-xboxdrv
```

## Start/stop the job

The `xboxdrv` job is already started when the package is installed. But, if for some reason, you need to restart it, run in terminal:

```term
sudo service xboxdrv restart
```
## Force Feedback

To enable force feedback, as `sudo` edit the `/etc/default/xboxdrv` file and change `FORCE_FEEDBACK` to `true`.

Then, restart the service: `sudo service xboxdrv restart`.

**One important note**: force feedback has problems with wine games.

## Additional Configurations Options

You can edit `/etc/default/xboxdrv` and add more configurations to `xboxdrv`.

To see a list of available configurations, please, check `xboxdrv` [options page](http://pingus.seul.org/~grumbel/xboxdrv/xboxdrv.html).

## PS3 dualshock

Some games supports only the X360 gamepad, but `xboxdrv` can force system to get Playstation 3 dualshock recognized as a X360 gamepad.

But with current Ubuntu kernel version (`3.13.0-29`) this is not properly working. The solution is to upgrade the kernel.

On [issue #11](https://github.com/raelgc/ubuntu_xboxdrv/issues/11) the kernel version `3.13.11-031311`  was reported to get the PS3 dualshock properly working.

## Uninstall

To uninstall, please use `purge` to remove the `xpad` stock driver from blacklist:

```term
sudo apt-get purge ubuntu-xboxdrv
```

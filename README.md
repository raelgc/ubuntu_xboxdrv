Ubuntu xboxdrv Integration
----------------------------

This package provides additional configurations over [`xboxdrv`](http://pingus.seul.org/~grumbel/xboxdrv/) driver.

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
- Manages a specific xboxdrv process per controller


## Install

To install (and automatically) start this service, open a terminal and run:

```term
sudo apt-add-repository -y ppa:rael-gc/ubuntu-xboxdrv
sudo apt-get update
sudo apt-get install ubuntu-xboxdrv
```

## Start/stop the job

The `xboxdrv` job is already started when the package is installed. But, if for some reason, you need to restart it, run in terminal:

```term
sudo service ubuntu-xboxdrv restart
```
## Force Feedback

To enable force feedback, as `sudo` edit the `/etc/default/xboxdrv` file and change `FORCE_FEEDBACK` to `true`.

Then, restart the service: `sudo service xboxdrv restart`.

**One important note**: force feedback has problems with wine games.

## Triggers

By default, triggers are not enabled as z-axis, but as buttons. To change, edit `/etc/defaults/xboxdrv` and change `TRIGGERS_AS_BUTTONS` to `false`.

## Configuring

Ubuntu-Xboxdrv is designed to be interacted with once. However this means that you must edit `/etc/default/xboxdrv`to have at least one controller setup. To to this, edit the following fields in the default file:
- `CONTROLLER1_OPTIONS` 
This field is for the arguements for `xboxdrv` that you would usually use with a specific controller. 
- `CONTROLLER1`
This field is for your controllers USB vendor:product keys. These values are easily found with an internet search for your device. 

In addition to having arguements added based on the controller, there is also a field to add arguements that are used with all controllers.

To see a list of available arguements to use, please, check `xboxdrv` [options page](http://pingus.seul.org/~grumbel/xboxdrv/xboxdrv.html). 
**One important note**: due to implimentation restrictions, it is recommended to avoid using controller slots, as this may cause issues.

## PS3 dualshock

Some games supports only the X360 gamepad, but `xboxdrv` can force system to get Playstation 3 dualshock recognized as a X360 gamepad.

If you'll connect by wireless (i.e., not wired by USB), please, first pair your dualshock by Bluetooth.

## Uninstall

To uninstall, please use `purge` to remove the `xpad` stock driver from blacklist:

```term
sudo apt-get purge ubuntu-xboxdrv
```

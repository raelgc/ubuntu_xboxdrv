Ubuntu xboxdrv Integration
----------------------------

Unlike stock xpad kernel driver, [`xboxdrv`](http://pingus.seul.org/~grumbel/xboxdrv/) provides a wide variety of configuration options: it allows you to simulate keyboard and mouse events, remap buttons and axes, apply autofire, invert axis, tweak axis sensitivity, emulate throttle and rudder controls and send macros.

But while xboxdrv is included in its last version on Ubuntu 14.04, it lacks additional configuration to get it properly working.

This package adds additional configurations over xboxdrv:

- It cleans broken configurations;
- Properly configure a upstart service;
- Manage xboxdrv service on System suspend/resume;
- Add support for user options at /etc/default/xboxdrv;
- Start with support for 4 joysticks;
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

## Configurations Options

You can edit `/etc/default/xboxdrv` and add more configurations to `xboxdrv`.

To see a list of available configurations, please, check `xboxdrv` [options page](http://pingus.seul.org/~grumbel/xboxdrv/xboxdrv.html).

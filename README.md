# homeassistant-bluetoothbulb.
Bluetooth bulbs custom component for Home Assistant

Mylight and MagicBlue (not currently working)

[MagicBlue](http://www.gearbest.com/smart-light-bulb/pp_230349.html) is a $9.99 bluetooth LED bulb.

<img src="https://github.com/xiaohuim/homeassistant-magicblue/raw/master/img/magicblue.jpg" height="350" /><img src="https://github.com/xiaohuim/homeassistant-magicblue/raw/master/img/homeassistant.jpg" height="350" /><img src="https://github.com/xiaohuim/homeassistant-magicblue/raw/master/img/homekit.jpg" height="350" />

## Requirement

- [`https://github.com/Betree/magicblue`](https://github.com/Betree/magicblue)

## Installation
Copy the `magicbluelight.py` file to :
```
<YOUR_CONFIG_DIR>/custom_components/light/magicbluelight.py
```

## Configuration
First, make sure you can see your MagicBlue(s) by running:
```
$ magicblueshell
Magic Blue interactive shell v0.2.2
Type "help" for a list of available commands
> help
 ----------------------------
| List of available commands |
 ----------------------------
COMMAND         PARAMETERS                    DETAILS
-------         ----------                    -------
help                                          Show this help
list_devices                                  List Bluetooth LE devices in range
ls              //                            //
connect         mac_address or ID             Connect to light bulb
disconnect                                    Disconnect from current light bulb
set_color       name or hexadecimal value     Change bulb's color
set_warm_light  intensity[0.0-1.0]            Set warm light
turn            on|off                        Turn on / off the bulb
exit                                          Exit the script
> ls
Listing Bluetooth LE devices in range for 5 minutes.Press CTRL+C to stop searching.
ID    Name                           Mac address
--    ----                           -----------
1     LEDBLE-XXXXXXXX                xx:xx:xx:xx:xx:xx
```

Modify the following example and add it to your `configuration.yaml` file:
```
light:
  platform: magicbluelight
    name: 'Living Room'
    address: 20:16:01:01:05:a0
    version: 9
```
Multiple devices are supported:
```
light:
  - platform: magicbluelight
    name: 'Living Room'
    address: 20:16:01:01:05:a0
    version: 9
  - platform: magicbluelight
    name: 'Bedroom'
    address: 20:16:01:01:03:e5
    version: 9
```

## Notes
- Right now you'll have to manually install the required python module `magicblue`.

## Todo
- [x] Brightness control
- [x] Color control
- [ ] Independent brightness and color control
- [x] Auto install the required module

# homeassistant-bluetoothbulb.
Bluetooth bulbs custom component for Home Assistant

Mylight and MagicBlue (not currently working)

[MagicBlue](http://www.gearbest.com/smart-light-bulb/pp_230349.html) is a $9.99 bluetooth LED bulb.

<img src="https://github.com/xiaohuim/homeassistant-magicblue/raw/master/img/magicblue.jpg" height="350" /><img src="https://github.com/xiaohuim/homeassistant-magicblue/raw/master/img/homeassistant.jpg" height="350" /><img src="https://github.com/xiaohuim/homeassistant-magicblue/raw/master/img/homekit.jpg" height="350" />

MyLight cheap ebay/amazon light with possbility to play music and change colors/effect/brightness

<img src="https://cdn.shopify.com/s/files/1/1026/2915/products/71sjF1R7SnL._SL1500_1024x1024.jpg?v=1499116245" width="300">

## Requirement

- [`https://github.com/Betree/magicblue`](https://github.com/Betree/magicblue)
- [`https://github.com/orrpan/mylight`](https://github.com/orrpan/mylight)

## Installation
Copy the `bluetoothbulb.py` file to :
```
<YOUR_CONFIG_DIR>/custom_components/light/bluetoothbulb.py
```


Modify the following example and add it to your `configuration.yaml` file:
```
light:
  platform: bluetoothbulb
    name: 'Living Room'
    address: 20:16:01:01:05:a0
    type: 'magicblue'
    version: 9
```
Multiple devices are supported:
```
light:
  - platform: bluetoothbulb
    name: 'Living Room'
    address: 20:16:01:01:05:a0
    type: 'mylight'
    version: 9
  - platform: bluetoothbulb
    name: 'Bedroom'
    address: 20:16:01:01:03:e5
    type: 'magicblue'
    version: 9
```

## Notes
MyLight does not support playing music, use another device for that (different bluetooth modules on bulb)

## Todo
- [x] Brightness control
- [x] Color control
- [ ] Independent brightness and color control
- [x] Auto install the required module

---
layout: page
title: "myStrom WiFi Bulb"
description: "Instructions how to integrate myStrom WiFi Bulbs into Home Assistant."
date: 2017-04-18 06:00
sidebar: true
comments: false
sharing: true
footer: true
logo: mystrom.png
ha_category: Light
---


The `mystrom` light platform allows you to control your [myStrom](https://mystrom.ch/en/) WiFi Bulbs. 

To use your myStrom WiFi Bulb in your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
light:
  - platform: mystrom
    host: IP_ADDRESS
    mac: MAC_ADDRESS
```

Configuration variables:

- **host** (*Required*): The IP address of your myStrom WiFi Bulb, eg. `192.168.1.32`.
- **mac** (*Required*): The MAC address of your myStrom WiFi Bulb, eg. `5AAC8CA542F3`.
- **name** (*Optional*): The name to use when displaying this light.

Check if you are able to access the light located at `IP_ADRRESS`. The details about your light is provided as a JSON response.

```bash
$ curl http://[IP_ADDRESS]/api/v1/device/[MAC_ADDRESS]

{
  "MAC_ADDRESS": {
    "type": "rgblamp",
    "battery": false,
    "reachable": true,
    "meshroot": false,
    "on": true,
    "color": "0;0;100",
    "mode": "hsv",
    "ramp": 409,
    "power": 5.1,
    "fw_version": "2.25"
  }
}
```


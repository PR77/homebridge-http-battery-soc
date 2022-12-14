<p align="center">
  <a href="https://github.com/homebridge/homebridge"><img src="https://raw.githubusercontent.com/homebridge/branding/master/logos/homebridge-color-round-stylized.png" height="140"></a>
</p>

<span align="center">

# homebridge-http-battery-soc

</span>

## Description

This [homebridge](https://github.com/homebridge/homebridge) plugin was inspired by (https://github.com/dhop90/homebridge-http-esp8266-battery) and based on the homebridge examples. This plugins exposes a web-based battery status to Apple's [HomeKit](http://www.apple.com/ios/home/). Using simple HTTP requests, the plugin displays the current SOC (State Of Charge) of a connected AGM battery.

## Installation

1. Install [homebridge](https://github.com/homebridge/homebridge#installation)
2. Install this plugin: `npm install -g homebridge-http-battery-soc`
3. Update your `config.json` file

## Configuration

```json
"accessories": [
     {
       "accessory": "esp8266Battery",
       "name": "esp8266Battery",
       "apiroute": "http://192.168.x.x,
       "pollInterval": 300,   //default (optional)
       "timeout": 10000       //default (optional)
     }
]
```

### Config

| Key | Description | Default |
| --- | --- | --- |
| `accessory` | Must be accessory | N/A |
| `name` | Name to appear in the Home app | N/A |
| `apiroute` | Root URL of your device | N/A |
| `pollInterval` | Time (in seconds) between device polls | `300` |
| `timeout` | Time (in milliseconds) until the accessory will be marked as _Not Responding_ if it is unreachable | `10000` |

### Response

Example of expected response for 50% State Of Charge (SOC)

```json
{
    "charge": 50
}
```

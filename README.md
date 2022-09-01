<p align="center">
  <a href="https://github.com/homebridge/homebridge"><img src="https://raw.githubusercontent.com/homebridge/branding/master/logos/homebridge-color-round-stylized.png" height="140"></a>
</p>

<span align="center">

# homebridge-http-esp8266-battery

</span>

## Description

This [homebridge](https://github.com/homebridge/homebridge) plugin was based upon (https://github.com/phenotypic/homebridge-web-garage). I've changed this to only exposes a web-based battery status to Apple's [HomeKit](http://www.apple.com/ios/home/). Using simple HTTP requests, the plugin displays the current SOC (State Of Charge) of a connected battery.

## Installation

1. Install [homebridge](https://github.com/homebridge/homebridge#installation)
2. Install this plugin: `npm install -g homebridge-http-esp8266-battery`
3. Update your `config.json` file

## Configuration

```json
"accessories": [
     {
       "accessory": "esp8266Battery",
       "name": "esp8266Battery",
       "apiroute": "http://192.168.x.x,
       "pollInterval": 300,   //default (optional)
       "timeout": 3000        //default (optional)
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
| `timeout` | Time (in milliseconds) until the accessory will be marked as _Not Responding_ if it is unreachable | `3000` |
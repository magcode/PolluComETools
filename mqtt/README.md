# PolluComE MQTT
This allows to send PolluComE data to MQTT.

# Installing
This guide is for running on a Raspberry Pi.

Make sure you have gcc and NodeJS installed.
The install script requires password less sudo permission. Do the steps in `install.sh` manually if you don't have this.

```
cd ~
git clone git@github.com:magcode/PolluComETools.git
PolluComETools/mqtt/install.sh
```

# Configuration
Before you start it the first time configure `mqtt/default.json`

```
{
  "mqtt": {
    "broker": "mqtt://broker",              // your mqtt host
    "topic": "home/heating/meter"           // your mqtt topic
  },
  "usbport": "/dev/ttyUSB1",                // USB port of the IR sensor
  "schedule": 15,                           // data will be send each 15 minutes
  "exec": "~/PolluComETools/mqtt/pollucom"  // you can leave this
}
```

# Starting
```
sudo service pollumq start
```

**Press the button** on your PolluCom E unit. After a short press, the unit will respond to IR signals for one hour.
Make sure you configure the `schedule` below 60 minutes.

# Uninstall

```
cd ~
PolluComETools/mqtt/uninstall.sh
```
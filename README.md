# node-red-simpel-afvalwijzer
Simple afwijzer.nl node setup, specificly for Synology HASS-core install.

In case you can NOT install the full featured version of afvalwijzer add-on, this is the easiest way to go.
ie for Synology HAS-core it's very hard to SSH everything to install the add-on's. Synology is not flexble on the install.

You need:
1. Node-red server running
2. MQTT server-running
3. Home Assistant running (on Synology)
4. Capable to edit your HASS config.yaml file (placed for synology at /usr/local/homeassistant/var/config/configuration.yaml

This is the way it works:
1. Node-red: scrape the API - use flow

uses the api-link from the afvalwijzer app, loads json data, and parses the next 4 events.

output is a json message containing the next 4 afvalwijzer events, postable for mqtt.
alternativly the result is 4 json message for mqtt

HomeAssistant: use the

simple, no sweat.

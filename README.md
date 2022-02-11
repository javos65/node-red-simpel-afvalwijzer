# node-red-simpel-afvalwijzer
simple afwijzer.nl node setup, specificly for Synology HAAS-core install

In case you can NOT install the full featured version of afvalwijzer, this is the easiest way to go
ie for Synology HAS-corem its has to SSH everything to install the add-on's

You need:
Node-red server running
MQTT server-running
Home Assistant running on Synology
Capable to edit your HASS config.yml file (placed for synology at

This is the way it works:
1. Node-red: scrape

uses the api-link from the afvalwijzer app, loads json data, and parses the next 4 events.

output is a json message containing the next 4 afvalwijzer events, postable for mqtt.
alternativly the result is 4 json message for mqtt

HomeAssistant: use the

simple, no sweat.

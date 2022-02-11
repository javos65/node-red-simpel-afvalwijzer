# node-red-simpel-afvalwijzer
simple afwijzer.nl node setup

In case you can NOT install the full featured version of 
ie for Synology HAS-core

uses the api-link from the afvalwijzer app, loads json data, and parses the next 4 events.

output is a json message containing the next 4 afvalwijzer events, postable for mqtt.
alternativly the result is 4 json message for mqtt

HomeAssistant: use the

simple, no sweat.

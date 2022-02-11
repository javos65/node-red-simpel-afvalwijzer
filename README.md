# node-red-simpel-afvalwijzer
Simple afwijzer.nl node setup, specificly for Synology HASS-core install.

In case you can NOT install the full featured version of afvalwijzer add-on, this is "the easiest way" to go.
ie for Synology HAS-core it's very hard to SSH everything to install the add-on's. Synology is not flexble on the install.

**You need:
**1. Node-red server running, ie on a raspi
**2. MQTT server-running, is on you synology or raspi
**3. Home Assistant running (on Synology)
**4. Capable to edit your HASS config.yaml file (placed for synology at /usr/local/homeassistant/var/config/configuration.yaml

This is the way it works:

#1. Node-red: scrape the API
Use afvalwijzer_flows.json to import
This uses the api-link from the afvalwijzer app, loads json data, and parses the next 4 events, spit it out to your mqtt server.
you can check the API call in your browser -  dont forget to change the zip code and the number.

run the node:
ie gft posts to : nodered/sensor/AFV/gft/state
json code is by example :
*{
  "device": "AFV",
  "name": "Afvalwijzer",
  "sequence": 0,
  "ntype": "gft",
  "type": "gft",
  "datum": "2022-02-14",
  "text": "14 Feb",
  "epoch": 1644796800000
}*

Same for 'papier', 'restafval' and 'plastic' 
Use MQttExplorer or any otehr mqtt app to check the results

#2. Home Assistant: edit your configuration.yaml
Add the mqtt-section to the "sensor: " part of your configuration file.
google around, there is enough info to figure this out.
on synology, the HomeAssistant config can be found at : /usr/local/homeassistant/var/config/configuration.yaml

Once done: restart HASS and check if you can see the sensors , ie 'sensor.afval_groen' or 'sensor.afval_papier'
(HASS is a nightmare if you have typo's in you configuration file, plz follow the error messages closely)

#3, the graphics picture... This is on synology acould be an issue, as the /local directory of HASS is not applicable.
Store your 'afvalwijzer.png' file in your local network at a http-adressable place.
I used the synology web page, as I had .php /.www setup. be smart.

#4 HASS: In you custom LoveLace (assuming you have this figured out), add the "Picture Elements Card"
The example code give you some idea, but replace it with the yaml code from "Picture Elements Card Configuration.yaml" file


simple, no sweat (at least it took me a day to get ths setup.. "trail and error methodology is holy"

- Jay

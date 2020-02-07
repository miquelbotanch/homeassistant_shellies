# Shelly MQTT check / upgrade Home Assistant's Package

 This package uses Shelly's ability to identify if is there is any update available (sensor) and, with a simple script execution, all of them can be upgraded at the same time.

 The query / upgrade process is done via MQTT server, so all shelly device MUST have configured MQTT server.

By default automation's check will run everyday at 20:00.

Enjoy and share !

Miquel Botanch

UI-LOVELACE Example
```
    - type: conditional
      conditions:
        - entity: sensor.shellies_can_be_updated
          state_not: "0"
      card:
        type: entities
        entities:
          - sensor.shellies_can_be_updated
          - script.mqtt_upgrade_all_shellies
```

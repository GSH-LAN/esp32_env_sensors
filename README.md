# ESP32 environmental sensors board

This PCB is a USB type C driven ESP32 board with two sensors (BME280, MH-Z19B).  
It's designed to be deployed during our LAN parties to record and send environmental data like temperature, humidity and CO₂-levels to our influx db.  
So that we are able to build fancy Grafana boards on top of it.

The board design is based on the [official *Espressive ESP32-DevKitC V4* schematics][esp_devkitc_schematics] and [@TobleMiner's][tobleminer] [USB type C implementation of the DevKit][tobleminer_devkit].

## Table of contents

- [ESP32 environmental sensors board](#esp32-environmental-sensors-board)
  - [Table of contents](#table-of-contents)
- [Sensors](#sensors)
  - [Bosh BME280](#bosh-bme280)
  - [Winsen MH-Z19B](#winsen-mh-z19b)
- [Features](#features)
- [Assembly -- TBD / WIP](#assembly----tbd--wip)

# Sensors

## Bosh BME280

The BME280 is as combined digital humidity, pressure and temperature sensor based on proven
sensing principles. The sensor module is housed in an extremely compact metal-lid LGA package with
a footprint of only 2.5 × 2.5 mm² with a height of 0.93 mm. Its small dimensions and its low power
consumption allow the implementation in battery driven devices such as handsets, GPS modules or
watches.

Source: BME280 data sheet  
[Data sheet][bme280_data_sheet]


## Winsen MH-Z19B

MH-Z19B NDIR infrared gas module is a common type, small size sensor, using non-dispersive infrared (NDIR)
principle to detect the existence of CO₂ in the air, with good selectivity, non-oxygen dependent and long
life. Built-in temperature compensation; and it has UART output and PWM output. It is developed by the
tight integration of mature infrared absorbing gas detection technology, precision optical circuit design and
superior circuit design

Source: MH-Z19B data sheet  
[Data sheet][wh-z19b_data_sheet]


# Features

  * USB type C
  * [WHC CH340G][ch340g_data_sheet] USB to serial interface (to program the ESP32)
  * [Bosh BME280][bme280_data_sheet]
    * Temperature sensor
    * Humidity sensor
    * Pressure sensor
  * [Winsen MH-Z19B][wh-z19b_data_sheet] CO₂ level sensor (optional)
  * Onboard WiFi antenna


# Assembly -- TBD / WIP

There is an [interactive HTML BOM][bom] to help you assemble the board.

Assuming you are using JLCPCB SMT assembly you will need to populate just the following parts by hand:

| Reference | Description            | LCSC       |
| --------- | ---------------------- | ---------- |
|           | USB Type C connector   | [C167321]  |
|           | RESET/BOOT push button | [C115357]  |
|           | Female header 1x4      | [C2718488] |
|           | Female header 1x5      | [C50950]   |


[esp_devkitc_schematics]: https://docs.espressif.com/projects/esp-idf/en/release-v4.4/esp32/hw-reference/esp32/get-started-devkitc.html#related-documents
[tobleminer]: https://github.com/TobleMiner
[tobleminer_devkit]: https://github.com/TobleMiner/ESP32-Devkit-Type-C
[bme280_data_sheet]: https://ae-bst.resource.bosch.com/media/_tech/media/datasheets/BST-BME280-DS002.pdf
[wh-z19b_data_sheet]: https://www.winsen-sensor.com/d/files/MH-Z19B.pdf
[ch340g_data_sheet]: http://www.wch-ic.com/downloads/file/79.html?time=2022-03-05%2004:29:24&code=w22QT3jQR4FM0SrIxIGGBQY0Q6dh2u690pWEflgr
[bom]: https://gsh-lan.github.io/esp32_env_sensors/ibom.html

[C167321]: https://lcsc.com/product-detail/USB-Connectors_Jing-Extension-of-the-Electronic-Co-C167321_C167321.html
[C115357]: https://lcsc.com/product-detail/Tactile-Switches_ALPS_SKRKAEE020_3-4-2-1-57N_C115357.html
[C2718488]: https://lcsc.com/product-detail/Female-Headers_BOOMELE-Boom-Precision-Elec-C2718488_C2718488.html
[C50950]: https://lcsc.com/product-detail/Female-Headers_BOOMELE-Boom-Precision-Elec-C50950_C50950.html
# ESP32 S-CAM Camera module

## Features

* The smallest 802.11b/g/n Wi-Fi BT SoC module.
* Low power 32-bit CPU, can also serve the application processor.
* Up to 160MHz clock speed, summary computing power up to 600 DMIPS.
* Built-in 520 KB SRAM, external 4MPSRAM.
* Supports UART/SPI/I2C/PWM/ADC/DAC.
* Support OV2640 and OV7670 cameras, built-in flash lamp.
* Support image WiFI upload.
* Supports TF card.
* Supports multiple sleep modes.
* Embedded Lwip and FreeRTOS.
* Supports STA/AP/STA+AP operation mode.
* Support Smart Config/AirKiss technology.
* Support for serial port local and remote firmware upgrades (FOTA).

## Specifications

* Wireless Module: ESP32-S WiFi 802.11 b/g/n + Bluetooth 4.2 LE module with PCB antenna, u.FL connector, 32Mbit SPI flash, 4MBit PSRAM.
* External Storage: micro SD card slot up to 4GB.
* Camera
  * FPC connector.
  * Support for OV2640 (sold with a board) or OV7670 cameras.
  * Image Format: JPEG( OV2640 support only ), BMP, grayscale.
  * LED flashlight.
* Expansion: 16x through-holes with UART, SPI, I2C, PWM.
* Misc: Reset button.
* Power Supply: 5V via pin header.
* Power Consumption.
  * Flash LED off: 180mA @ 5V.
  * Flash LED on to maximum brightness: 310mA @ 5V.
  * Deep-sleep: 6mA @ 5V min.
  * Modem-sleep: 20mA @ 5V min.
  * Light-sleep: 6.7mA @ 5V min.
* Dimensions (ESP32): 40 x 27 x 12 (LxWxH) mm.
* Temperature Range: Operating: -20 ℃ ~ 85 ℃; storage: -40 ℃ ~ 90 ℃ @ < 90%RH.

## Pinout
![image](https://user-images.githubusercontent.com/44589560/195549429-37e73d4e-082c-44f9-8b3e-816c8f901346.png)

## Module settings screen

When connected to ESP32-CAM-MB my module had IP: http://192.168.4.1/


![Skærmbillede (9)](https://user-images.githubusercontent.com/44589560/195547686-b3e29914-a9de-4411-bbb5-09edee03b268.png)

## Uploading the  code

First - had difficulty with uploading the code until I read a jumper should be placed from GPIO0 to GND. After that there was no trouble uploading the code.

## References and sources

* https://all3dp.com/2/esp32-cam-arduino-tutorial/#i-3-1-ftdi-cable
* [How to setup ESP32 Camera using Arduino IDE and Arduino UNO](https://robojax.com/learn/arduino/?vid=robojax_ESP32_camera)
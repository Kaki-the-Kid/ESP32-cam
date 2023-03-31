# ESP32 Cam - Save image to Micro SDCard

## Arduino Libraries
SD Card ESP32<br />
* FS.h             // SD Card ESP32
* SD_MMC.h         // SD Card ESP32

Driver files for the ESP32-CAM board<br />
* esp_camera.h

You can find the driver files for the ESP32-CAM board here:<br />
https://github.com/espressif/esp32-camera


* soc/soc.h           // Disable brownout problems
* soc/rtc_cntl_reg.h  // Disable brownout problems

 You can find the driver files Espressif IoT Development Framework:<br />
 https://github.com/pycom/esp-idf-2.0/blob/master/components/esp32/include/soc/soc.h


#include "driver/rtc_io.h"
#include <WiFi.h>
#include "time.h"

## Functionality
![image](https://user-images.githubusercontent.com/44589560/226575802-6e7793ba-fd1e-4426-a73e-59a2b4ab5273.png)

1. Connect to WiFi
2. Connect to NTP server
3. Initialize SDCard
4. Initialize Camera
5. Camera takes a picture
6. Get time from NTP server
7. Save image to SDCard
8. Repeat from step 5

The filename is the current time in the format `YYYYMMDD_HHMMSS.jpg`
Easy organization of images by date and time.
No need to worry about overwriting images.

## Hardware - Parts List

* ESP32 Cam<br />
This example is made with the OV2640 camera module.
* Micro SDCard

## Format Micro SDCard

I suggest formatting your microSD card as the first step. You can either use the Windows formatter tool or any other software specifically designed for microSD formatting.

    Right click on the microSD card and select Format. 
    Select FAT32 as the file system and click Start.

Just so you know, the ESP32-CAM is supposed to work with only 4 GB SD cards. But guess what? We tried using a 16 GB SD card, and it worked perfectly fine!

## Installing the ESP32 add-on

## Troubleshooting

![image](https://user-images.githubusercontent.com/44589560/226612891-7e416f93-3d54-4b5b-9573-27fd248b6d9a.png)

## Future xpansions

![image](https://user-images.githubusercontent.com/44589560/226619551-a9b74862-0a58-4555-b1c8-d42d1cb94d88.png)

## References and sources

* [ESP32-CAM Take Photo and Save to MicroSD Card](https://randomnerdtutorials.com/esp32-cam-take-photo-save-microsd-card/)
* [ESP32-CAM Take Photo and Save to MicroSD Card with Date and Time (timestamp)](https://randomnerdtutorials.com/esp32-cam-photo-microsd-card-timestamp/)
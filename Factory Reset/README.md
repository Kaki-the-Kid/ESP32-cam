# ESP32 - Factory Reset
This is a simple example to demonstrate how to reset the ESP32 to factory defaults.
It will erase the NVS partition and restart the ESP32. In essence erase the ESP32 flash memory to restore it to its original state.

So you can delete any changes made to the firmware or configuration settings. This has a good chance of fixing any problems you might be having with the ESP32 if it is crashing constantly and you can’t upload new code. It will also clear data that is no longer needed, and other applications.

## How it works

We can use a python based tool called esptool. This example is made with version 4.5.1.

> A Python-based, open-source, platform-independent utility to communicate with the ROM bootloader in Espressif chips.

* You can find the tool here:<br />https://pypi.org/project/esptool/
* You can find the documentation here:<br />https://docs.espressif.com/projects/esptool/en/latest/esp32/

## Step 1: Install esptool
Prerequisite Python 3.7 or later

```
pip install esptool
```
If this give any erros, try this:
``` 
pip install --upgrade pip
pip install esptool
```
or
```
python -m pip install esptool
```
## Step 2: Install setuptools
Setup tools is a collection of enhancements to the Python distutils that allow you to more easily build and distribute Python packages, especially ones that have dependencies on other packages. It’s a package that’s used by other packages, so it’s a good idea to install it first. This is required for the next step. In my version is was already install.

```
pip install setuptools
```
Test that everything is installed correctly:
```
python -m setuptools --version
python -m esptool
```

last command should give you this output:
```
esptool.py v4.5.1
usage: esptool [-h]
               [--chip {auto,esp8266,esp32,esp32s2,esp32s3beta2,esp32s3,esp32c3,esp32c6beta,esp32h2beta1,esp32h2beta2,esp32c2,esp32c6,esp32h2}]
               [--port PORT] [--baud BAUD] [--before {default_reset,usb_reset,no_reset,no_reset_no_sync}]
               [--after {hard_reset,soft_reset,no_reset,no_reset_stub}] [--no-stub] [--trace]
               [--override-vddsdio [{1.8V,1.9V,OFF}]] [--connect-attempts CONNECT_ATTEMPTS]
               {load_ram,dump_mem,read_mem,write_mem,write_flash,run,image_info,make_image,elf2image,read_mac,chip_id,flash_id,read_flash_status,write_flash_status,read_flash,verify_flash,erase_flash,erase_region,merge_bin,get_security_info,version}
               ...

esptool.py v4.5.1 - Espressif chips ROM Bootloader Utility

positional arguments:
  {load_ram,dump_mem,read_mem,write_mem,write_flash,run,image_info,make_image,elf2image,read_mac,chip_id,flash_id,read_flash_status,write_flash_status,read_flash,verify_flash,erase_flash,erase_region,merge_bin,get_security_info,version}
                        Run esptool.py {command} -h for additional help
    load_ram            Download an image to RAM and execute
    dump_mem            Dump arbitrary memory to disk
    read_mem            Read arbitrary memory location
    write_mem           Read-modify-write to arbitrary memory location
    write_flash         Write a binary blob to flash
    run                 Run application code in flash
    image_info          Dump headers from an application image
    make_image          Create an application image from binary files
    elf2image           Create an application image from ELF file
    read_mac            Read MAC address from OTP ROM
    chip_id             Read Chip ID from OTP ROM
    flash_id            Read SPI flash manufacturer and device ID
    read_flash_status   Read SPI flash status register
    write_flash_status  Write SPI flash status register
    read_flash          Read SPI flash content
    verify_flash        Verify a binary blob against flash
    erase_flash         Perform Chip Erase on SPI flash
    erase_region        Erase a region of the flash
    merge_bin           Merge multiple raw binary files into a single file for later flashing
    get_security_info   Get some security-related data
    version             Print esptool version

options:
  -h, --help            show this help message and exit
  --chip {auto,esp8266,esp32,esp32s2,esp32s3beta2,esp32s3,esp32c3,esp32c6beta,esp32h2beta1,esp32h2beta2,esp32c2,esp32c6,esp32h2}, -c {auto,esp8266,esp32,esp32s2,esp32s3beta2,esp32s3,esp32c3,esp32c6beta,esp32h2beta1,esp32h2beta2,esp32c2,esp32c6,esp32h2}
                        Target chip type
  --port PORT, -p PORT  Serial port device
  --baud BAUD, -b BAUD  Serial port baud rate used when flashing/reading
  --before {default_reset,usb_reset,no_reset,no_reset_no_sync}
                        What to do before connecting to the chip
  --after {hard_reset,soft_reset,no_reset,no_reset_stub}, -a {hard_reset,soft_reset,no_reset,no_reset_stub}
                        What to do after esptool.py is finished
  --no-stub             Disable launching the flasher stub, only talk to ROM bootloader. Some features will not be
                        available.
  --trace, -t           Enable trace-level output of esptool.py interactions.
  --override-vddsdio [{1.8V,1.9V,OFF}]
                        Override ESP32 VDDSDIO internal voltage regulator (use with care)
  --connect-attempts CONNECT_ATTEMPTS
                        Number of attempts to connect, negative or 0 for infinite. Default: 7.
```

## Step 3: Erase the flash memory


```
esptool.py --chip esp32 --port COM3 erase_flash
```



## How to use example
### Hardware Required
This example does not require any special hardware.

### Configure the project
```
idf.py menuconfig
``` 
Set serial port under Serial Flasher Options.


### Build and Flash
Build the project and flash it to the board, then run monitor tool to view serial output:
``` 
idf.py -p PORT flash monitor
```
Replace PORT with the serial port name of your board.


## Reference
https://randomnerdtutorials.com/esp32-erase-flash-memory/


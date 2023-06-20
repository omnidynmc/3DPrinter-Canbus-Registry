# HOWTO

## Find USB devices serial id

````
ls -al /dev/serial/by-id/
````

If you get a "no such file or directory" error, that means no USB devices are recognized by the system. It could be as simple as a bad cable, loose connection or more complex, like the device isn't in boot (DFU) mode.

## Flash STM devices from Raspberry Pi

````
sudo dfu-util -a 0 -D <path to .bin> --dfuse-address 0x08000000:force:mass-erase:leave -d 0483:df11
````

## Flash Canboot from Raspberry Pi

From inside of the Canboot folder run the following command after compiling:

````
make flash FLASH_DEVICE=<device id>
````

## View list of USB devices the Raspberry Pi detects

````
lsusb
````
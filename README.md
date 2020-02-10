# nodemcu
resources for nodemcu (esp8266)

## flash micropython
[Follow the steps here to flash the firmware](https://docs.micropython.org/en/latest/esp8266/tutorial/intro.html)
(basically the following):
1. [Download micropython firmware](http://micropython.org/download#esp8266)
2. `pip install esptool`
3. Find the usb interface the board is connected to, likely `/dev/ttyUSB0`  
4. Erase flash `esptool.py --port /dev/ttyUSB0 erase_flash`
5. Flash micropython `esptool.py --port /dev/ttyUSB0 --baud 460800 write_flash --flash_size=detect 0 ~/Downloads/esp8266-20190529-v1.11.bin`

The best way to connect to the repl and transfer files is via mpfshell (rshell is good too but I've had some issues with it not connecting to the board).

## [mpfshell](https://github.com/wendlers/mpfshell)
- open mpfshell `mpfshell`
- connect to board `open ttyUSB0` (don't type `/dev/`)

## [rshell](https://github.com/dhylands/rshell)
- open rshell `rshell`
- connect to board `connect serial /dev/ttyUSB0`

- if rshell keeps failing to connect try flashing the board with `--flase_size=4MB` like this: 
  `esptool.py --port /dev/cu.SLAB_USBtoUART --baud 115200 write_flash --verify --flash_size=4MB -fm dout 0 Desktop/esp8266-20190125-v1.10.bin` from [this forum](https://forum.micropython.org/viewtopic.php?f=2&t=5951&start=10)

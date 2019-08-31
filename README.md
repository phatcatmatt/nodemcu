# nodemcu
resources for nodemcu

1. erase flash `esptool.py --port /dev/ttyUSB0 erase_flash`
2. flash micropython `esptool.py --port /dev/ttyUSB0 --baud 460800 write_flash --flash_size=detect 0 ~/Downloads/esp8266-20190529-v1.11.bin`
3. open rshell `rshell`
4. connect to board `connect serial /dev/ttyUSB0`


### notes
- if rshell keeps failing to connect try flashing the board with `--flase_size=4MB` like this: 
  `esptool.py --port /dev/cu.SLAB_USBtoUART --baud 115200 write_flash --verify --flash_size=4MB -fm dout 0 Desktop/esp8266-20190125-v1.10.bin` from [this forum](https://forum.micropython.org/viewtopic.php?f=2&t=5951&start=10)

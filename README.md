# DMComm

Arduino program and library to communicate with Digimon toys, by BladeSabre ( bladethecoder@gmail.com ). License: MIT.

Loosely based on `dmcomm-python`, but avoiding dynamic allocation (except in SerialFollower).

## Installation
* Clone the repo into your Arduino libraries directory, then open the ClassicComUnit example
* Find the [Arduino15 folder](https://support.arduino.cc/hc/en-us/articles/360018448279-Open-the-Arduino15-folder)
* ATmega32U4:
  * Increasing the serial buffer is not required
* Nano/Uno:
  * From the Arduino15 folder, go to `packages/arduino/hardware/avr/{version}`
  * Create `platform.local.txt` containing `compiler.cpp.extra_flags=-DSERIAL_RX_BUFFER_SIZE=128`
  * Restart the Arduino IDE
* Bazjo D-Com:
  * Install [MiniCore](https://github.com/MCUdude/MiniCore#how-to-install)
  * From the Arduino15 folder, go to `packages/minicore/hardware/avr/{version}`
  * Open `boards.txt`
  * Find the line `328.build.extra_flags={build.clkpr}`
  * Add to the end of that line, so that it says:
     * `328.build.extra_flags={build.clkpr} -DSERIAL_RX_BUFFER_SIZE=128`
  * Restart the Arduino IDE
  * From the Tools menu, select `Board:MiniCore:ATmega328` and `Variant:328PB` (leave the other board options alone)

## Other DMComm versions
* For the original version which is not a library, see https://github.com/dmcomm/dmcomm-project
* For the CircuitPython version for RP2040, see https://github.com/dmcomm/dmcomm-python

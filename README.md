# Custom split keyboard

This repository contains useful info about making custom keyboards, which

## Useful links

Below are some useful information about parts of keyboard. Every section ends with few useful links.

### PCB

- [Guide for creating PCB](https://github.com/ruiqimao/keyboard-pcb-guide)
- [Colosseum PCB](https://github.com/swanmatch/colosseum60)
- [ErgoDox PCB](https://github.com/Ergodox-io/ErgoDox)
- [Cherry MX PCB](https://github.com/ogatatsu/Cherry-Mx-Bitboard)
- [key switches PCB](https://github.com/daprice/keyswitches.pretty)

### Microcontrollers

There are few options, Arduino Pro Micro with Atmega32, STM32, Elite C microcontroller (_like Pro Micro, but with USB C and some other improvements_)

- [Pro micro vs Elite article](https://docs.splitkb.com/hc/en-us/articles/360011510839-Pro-Micro-vs-Elite-C-Why-choose-one-over-the-other-)
- [Another microcontroller discussion on reddit](https://www.reddit.com/r/MechanicalKeyboards/comments/fs7dxb/is_the_atmega32u4_the_best_microcontroller_for/)
- [Firmware QMK documentation](https://beta.docs.qmk.fm)
- [Github project QMK firmware](https://github.com/qmk/qmk_firmware)
- [QMK firmware online configuration](https://config.qmk.fm/#/handwired/dactyl_promicro/LAYOUT_6x6)
- [Github project TKM keyboard firmware](https://github.com/tmk/tmk_core) with firmware for Atmel AVR and Cortex-M

### Shops

- [splitkb](https://splitkb.com/)

### Switches

- [switch specifications](https://www.reddit.com/r/MechanicalKeyboards/comments/a7stdo/information_on_kailh_choc_switches/)

## Whats you need

- switches
- keycaps
- microcontroller (_arduino pro micro_)
- diodes
- [TRRS](https://en.wikipedia.org/?title=TRRS_connector&redirect=no), RJ9 or conectors and cable
- USB cable

## Other

- [Nice custom build video](https://www.youtube.com/watch?v=y0F8Mig40m0)

- [QMK documentation](https://docs.qmk.fm)

```C
// wiring of each half
#define MATRIX_COL_PINS { B5, B4, E6, D7, C6, D4 }
#define MATRIX_ROW_PINS { F6, F7, B1, B3, B2 }
```

Can be also used only for only one side with append define name with side. For example: `MATRIX_COL_PINS_RIGHT`.

## Bootloader

## Keyboard layout

For translate `json` keyboard layout to `.c` can be used [this side](https://jhelvy.shinyapps.io/qmkjsonconverter/).

## Building keyboard

[Here](https://sachee.medium.com/building-my-first-keyboard-and-you-can-too-512c0f8a4c5f) is really nice guide about building your own dactyl keyboard.

## Flashing keyboard

For flash your keyboard you can use [QMK Toolbox](https://github.com/qmk/qmk_toolbox) (_but it is not available on linux_) with gui, [QMK CLI](https://github.com/qmk/qmk_cli) or make file in qmk repository

QMK CLI

```
sudo qmk flash -kb <keyboard> -km <layout>
```

If you want compile to hex file, you can use `compile` instead `flash`.

Make:

```
sudo make <keyboard>:<layout>:flash
```

You can also use make without flash for compilation.

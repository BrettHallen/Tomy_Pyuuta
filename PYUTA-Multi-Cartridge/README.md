# TOMY Pyūta Multi Cartridge

Original repository (Japanese):<br>
https://github.com/yanataka60/PYUTA-GBASIC-Multi-Cartridge

![Multi Cartridge](https://github.com/yanataka60/PYUTA-Multi-Cartridge/blob/main/JPEG/TITLE.jpg)

Inufutoさん has generously published many self-made programs for retro PCs, and for the ぴゅう太 (Pyūta) they are released as ROM images.

So [I (yanataka60)](https://github.com/yanataka60) created a cartridge that allows you to easily switch between those ROM images using DIP switches and enjoy them on real hardware.

The published ROM images come in two types: (>8000～) and (>4000～).  
Use the **16KB (8KB) ROM Multi Cartridge** for (>8000～) images and the **32KB ROM Multi Cartridge** for (>4000～) images.

**Note:** To use the 32KB ROM Multi Cartridge on the original (first-generation) ぴゅう太, a game adapter equivalent is required.  
Inserting the 32KB ROM Multi Cartridge directly into the original ぴゅう太 cartridge slot will **not** work.

The 16KB (8KB) ROM Multi Cartridge has been tested working on ぴゅう太 and ぴゅう太 mk2.  
The 32KB ROM Multi Cartridge has been tested working on ぴゅう太 + game adapter equivalent, and ぴゅう太 mk2.  
Both types are expected to work on the ぴゅう太 Jr. as well.

Of course, you will need a separate ROM programmer/writer device to burn the images into the EPROMs.

## 16KB (8KB) ROM Multi Cartridge

### Schematic
Please refer to `PYUTA16k.pdf` in the KiCad folder.

[ schematic ](https://github.com/yanataka60/PYUTA-Multi-Cartridge/blob/main/Kicad/16K/PYUTA16k.pdf)

![16K](https://github.com/yanataka60/PYUTA-Multi-Cartridge/blob/main/Kicad/16K/PYUTA16k_1.jpg)

### Parts List

| Ref  | Part name                        | Qty | Notes                              |
|------|----------------------------------|-----|------------------------------------|
| U1–U4| ROM 27512                        | 1–4 | Up to 4 pieces                     |
| U5   | 74LS138                          | 1   |                                    |
| U6   | 74LS32                           | 1   |                                    |
| SW1  | DIP switch 4-position            | 1   | e.g. Akizuki EDS104SZ etc.         |
| R1–R4| Carbon resistor 10KΩ             | 4   |                                    |
| C1–C4, C6, C7 | Multilayer ceramic capacitor 100nF | 6 | |
| C5   | Electrolytic capacitor 16V 100µF | 1 | |
|      | 28-pin IC socket                 | 4   |                                    |
|      | 16-pin IC socket                 | 1   | Optional                           |
|      | 14-pin IC socket                 | 1   | Optional                           |

### Writing to ROM
Write the ROM images to each 27512 starting at the following addresses:
- 0000h
- 4000h
- 8000h
- C000h

### ROM Image Selection
- DIP switch positions 1 and 2 select the bank: 0000h / 4000h / 8000h / C000h  
- DIP switch positions 3 and 4 select which ROM chip (U1–U4) is active.

Up to **16 different ROM images** can be selected.

## 32KB ROM Multi Cartridge

### Schematic
Please refer to `PYUTA32k.pdf` in the KiCad folder.

[ schematic ](https://github.com/yanataka60/PYUTA-Multi-Cartridge/blob/main/Kicad/32K/PYUTA32k.pdf)

![32K](https://github.com/yanataka60/PYUTA-Multi-Cartridge/blob/main/Kicad/32K/PYUTA32k_1.jpg)

### Parts List

| Ref  | Part name                        | Qty | Notes                              |
|------|----------------------------------|-----|------------------------------------|
| U1–U4| ROM 27512                        | 1–4 | Up to 4 pieces                     |
| U5   | 74LS138                          | 1   |                                    |
| U6   | 74LS32                           | 1   |                                    |
| U7   | 74LS04                           | 1   |                                    |
| U8   | 74LS08                           | 1   |                                    |
| SW1  | DIP switch 4-position            | 1   | Akizuki EDS104SZ etc. (only 3 bits used, 3-position switch is also OK) |
| R2–R4| Carbon resistor 10KΩ            | 3   |                                    |
| C1–C4, C6–C9 | Multilayer ceramic capacitor 100nF | 8 | |
| C5   | Electrolytic capacitor 16V 100µF | 1 | |
|      | 28-pin IC socket                 | 4   |                                    |
|      | 16-pin IC socket                 | 1   | Optional                           |
|      | 14-pin IC socket                 | 3   | Optional                           |

### Writing to ROM
Write the ROM images to each 27512 starting at the following addresses:
- 0000h
- 8000h

### ROM Image Selection
- DIP switch position 1 selects the bank: 0000h / 8000h  
- DIP switch positions 2 and 3 select which ROM chip (U1–U4) is active.

Up to **eight different ROM images** can be selected.

## Acknowledgements
Thank you very much to Inufutoさま for releasing so many wonderful games.
Thank you to Enriさま for publishing detailed technical information about the ぴゅう太.

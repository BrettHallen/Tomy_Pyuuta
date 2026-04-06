# Tomy Pyūta<br>トミーぴゅう太
Information about the Tomy Pyūta (TP1000), Pyūta Mk II (TP1007) and Pyūta Jr. (TP2001).  This computer was also seen in the West as the Tomy Tutor, but I don't have one of those and I'm sure there's plenty of English-language information already easily found.

Sorry about the mixed use of:
- ぴゅう太 (pyuuta)
- Pyuuta
- Pyuta
- Pyūta (pyuuta)
- Puuta (on motherboard)
- Mk II
- Mk 2
- mkII
- Mark 2
- Mark II
- etc.

### Pyūta TP1000
![The TP1000](/Images/Tomy_Pyuuta_TP1000_small.png)

### Pyūta mkII TP1007
The motherboard names it as the TUTOR-MKII.
![The TP1007](/Images/Tomy_Pyuuta_mkII_TP1007_small.png)

## YouTube Videos
### Pyūta (TP1000)
- [Part 1: Power On](https://youtu.be/n1GbW3sMFAQ)
- [Part 2: New Power Supply & Game Adaptor](https://youtu.be/_u84HEhmOtU)

### Pyūta mkII (TP1007)
- [Part 1: First Look](https://youtu.be/pd9VcPLzIxA)

## [Japanese G-BASIC Statements](/Japanese_G-BASIC)
My attempt at making sense of the unique Japanese version of BASIC (日本語G-BASIC) on the original ぴゅう太.

## [Universal Power Supply](/Tomy_Pyuuta_Power_Supply)
The Japanese ぴゅう太 is designed for a 100VAC input.<br>

The power supply outputs regulated +12VDC (via an LM7812), regulated -5VDC (via a TA78L005AP) and unregulated +5VDC (about +7.8V unloaded, 5.3V under load).  Yes, that is not a mistake ... the regulated -5V rail uses a 7805.<br>

The power LED is also connected to the -5V rail.<br>

I have designed a simple replacement as we use 240VAC here in Australia.<br>

It takes a regulated 12VDC input (3-4A) and generates the required ±5VDC via switching regulators, and passes the +12VDC straight through.<br>

![Universal power supply](/Tomy_Pyuuta_Power_Supply/Tomy_Pyuuta_Power_Supply_3D_small.png)

## Pyūta mkII Video Mod
It seems that Tomy removed the baseband A/V output that was in the original TP1000 from the mkII, leaving it with just the RF modulated output.  I created a [quick schematic of the video output](/Schematics/Tomy_Pyuuta_mkII_AV) in the mkII to use as a basis, and found an [RC2014 expansion board that adds a TMS9918 video output](https://github.com/jblang/TMS9918A) which I could use as a reference.<br>

It seems to work okay!  I am planning to replace the TMS9918 with a [Pico9918](https://github.com/visrealm/pico9918) anyway.<br>

| Component | Original value | Modified value | Notes                                               |
|-----------|----------------|----------------|-----------------------------------------------------|
| R2        | 33Ω            | 75Ω            | Impedance matching                                  |
| R3        | 33Ω            | 0Ω link        |                                                     |
| R4        | 560Ω           | 470Ω           | Values are close, don't bother?                     |
| R5        | 8.2Ω           | Ferrite bead   |                                                     |
| C4        | 330pF          | 100nF to GND   | Connect from Q1 collector to GND                    |
| C49       | 47nF           | Remove         | 12V decoupling, not needed if RF modulator removed? |

## [Game Adaptor](/Pyuuta_Game_Adaptor)
My attempt at a homebrew version of the Pyūta Game Adaptor seeing as most of the information seems to have been lost.<br>

The Game Adaptor allows the original Pyūta (TP1000) to run 32KB cartridges designed for the Mk II (TP1007) and Jr. (TP2001).<br>

![Game Adaptor original](/Images/Tomy_Pyuuta_Game_Adaptor_2_small.png)

## Sources
- [yanataka60](https://github.com/yanataka60)

## Useful links
- [Floodgap Systems](https://www.floodgap.com/retrobits/tomy/)
- [Cartridge archive](https://www.classicplastic.net/helpline/)
- [Leaded Solder's Blog](https://www.leadedsolder.com/2023/03/14/tomy-pyuuta-pickup-keyboard-power-switch-repair.html)
- [Classic Plastic (software)](https://www.classicplastic.net/helpline/)

## [Recovered Info](/Recovered_Info)
Useful information I've found from either Japanese-language websites (so not easy for the non-Japanese to find) or from vanished websites that have been lost.  I absolutely do not claim any credit for the useful info contained.<br>

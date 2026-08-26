# FM-NEW7 ROMs
These are raw dumps from my machine.  I think they probably need some sort of manipulation to use in an emulator, but should be usable as-is to burn new, physical ROMs.<br>

A complete list can be found [here](https://haserin09.la.coocan.jp/fm7rom.html).<br>

## BOOT (M73)
This is an MB8516 EPROM (2716) marked "TL11-11".<br>
It contains four 512-byte banks selected by SW2-1 (A9) and SW2-2 (A10):
- bank 0 = ROM boot (i.e. F-BASIC) [on/on]
- bank 1 = bubble memory boot [off/on]
- bank 2 = disk boot [on/off]
- bank 3 = halt (no boot) [off/off]

If bubble memory or disk boot is selected and those peripherals are not installed, the machine will hang with a continuous tone from the speaker.<br>

If halt/no boot is selected then the machine will not boot and just show a flashing cursor.<br>

## BASIC (M74)
This is an MB83256 masked ROM (27256) with code 160.<br>
- code 107 = F-BASIC v3.00 (FM-7)
- code 128 = F-BASIC v3.01 (FM-7, FM-NEW7 initial)
- code 160 = F-BASIC v3.02 (FM-NEW7 final)

## SUBSYS-C (M60)
This is an MB83256 masked ROM (27256) with code 167.<br>
It is the character generator & subsystem monitor ROM.


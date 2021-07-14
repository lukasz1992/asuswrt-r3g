# AsusWRT Xiaomi
This is version of AsusWRT that works with Xiaomi Mi routers

## Supported devices
- Xiaomi MI R3G v1 - use R3G firmware
- Xiaomi MI R3G v2 and R4A - use R4A firmware
- Xiaomi AC2100, Xiaomi Redmi AC2100 - use R2100 firmware for black (cylinder) variant and use RM2100 firmware for white (6 antennas) variant
- Xiaomi R3P - use R3P firmware

## How to install
1. Download image from Releases page or build it from source
2. Flash it to a router from stock firmware or bootloader

## Installation from stock firmware
Installation process is similar to OpenWRT
- NAND flash - image needs to be split into two parts: first 4MB and the rest - first part needs to be written to kernel1 partition, the rest to rootfs0. nvram variable flag_try_sys1_failed needs to be to 1, kernel0 partition should be erased
- NOR flash - image needs to be written to OS1 or linux partition

## Installation from bootloader
- NAND flash - image needs to be written at 0x600000 offset
- SPI flash on MI Wifi Mini - image needs to be written at 0x50000 offset
- SPI flash - image needs to be written at 0x180000 offset

## How to build image from source
1. cd release/src-ra-5010 (cd release/src-ra-mt7620 for MI Wifi Mini)
2. make model (currently available models are: rt-mir3g, rt-mir4a, rt-rm2100, rt-r2100)

## Missing features
- No dual-wan support on MT7621 devices

## Important note
- I do not take responsibility for any damages - you do everything on your own risk

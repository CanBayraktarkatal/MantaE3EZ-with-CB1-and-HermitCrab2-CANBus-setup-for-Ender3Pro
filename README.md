# Manta E3EZ V1.0 + CB1 V2.2 + Hermit Crab V2.0 CAN Bus Setup for Ender 3 Pro
## Introduction
I have prepared this document to outline the steps required to set up the CAN (Control Area Network) Bus for Manta E3EZ V1.0, CB1 V2.2, and Hermit Crab V2.0 CAN Version.

I have used the following boards and components:
- [BIGTREETECH Manta E3EZ V1.0 Board](https://biqu.equipment/products/bigtreetech-manta-e3ez-v1-0-for-ender3-ender3pro-ender5 "BIGTREETECH Manta E3EZ V1.0")
- [BIGTREETECH CB1 V2.2](https://biqu.equipment/products/pi4b-adapter-v1-0?variant=40353646051426 "BIGTREETECH CB1 V2.2")
- [BIQU Hermit Crab V2.0 - CAN Version](https://biqu.equipment/products/biqu-hermit-crab-v2-0-quick-change-extruder-hotend-tool-for-3d-printing?variant=40703888883810 "BIQU Hermit Crab V2.0 - CAN Version")
- Micro SD card
- Micro SD card reader
- Micro USB cable
- USB-C cable

## Table of Contents
1. [CB1 to E3EZ Installation and Mainsail Setup](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/CB1%20to%20E3EZ%20Installation%20and%20Mainsail%20Setup.md "CB1 to E3EZ Installation and Mainsail Setup")
2. [CAN Bus Setup on CB1](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/CAN%20Bus%20Setup%20on%20CB1.md "CAN Bus Setup on CB1")
3. [Connect Hermit Crab V2.0 to E3EZ](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Connect%20Hermit%20Crab%20V2.0%20to%20E3EZ.md "Connect Hermit Crab V2.0 to E3EZ")

## Sources
- BIGTREETECH Manta E3EZ V1.0 Board - [User Manual](https://github.com/bigtreetech/Manta-E3EZ/blob/master/BIGTREETECH%20Manta%20E3EZ%20V1.0%20User%20Manual.pdf "BIGTREETECH Manta E3EZ V1.0 Board")
- BIGTREETECH CB1 V2.2 - [User Manual](https://github.com/bigtreetech/CB1/blob/master/BIGTREETECH%20CB1%20User%20Manual.pdf "BIGTREETECH CB1 V2.2")
- Biqu Hermit Crab V2.0 CAN Version - [User Manual](https://github.com/bigtreetech/HermitCrab/blob/master/HermitCrab2/Hermit%20Crab%202%20CAN%20User%20Manual.pdf "Biqu Hermit Crab V2.0 CAN Version")
- Arksine’s “Katapult” [Repository](https://github.com/Arksine/katapult "Katapult Repository")
- Fredrik Åsberg’s “BTT Manta M8P v1.1 + BTT EBB 2209 Canbus setup” [Repository](https://gist.github.com/fredrikasberg/c14f08eb8617bf8981f77dbc01b00602 "BTT Manta M8P v1.1 + BTT EBB 2209 Canbus setup Repository")
- Hobbyist Notes’ “Klipper CAN BUS Guide - BIGTREETECH E3EZ with Hermit Crab 2” [Video](https://www.youtube.com/watch?v=GfUMAPoJlR4 "Klipper CAN BUS Guide Video")


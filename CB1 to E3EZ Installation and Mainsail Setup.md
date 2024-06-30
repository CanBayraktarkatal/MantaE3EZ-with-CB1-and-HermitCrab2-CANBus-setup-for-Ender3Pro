## CB1 to E3EZ Installation and Mainsail Setup
### CB1 Antenna Connection
Before installing CB1 onto E3EZ, connect its antenna.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/1.png)

### CB1 to E3EZ Installation
E3EZ has the space to install CB1 onto the board.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/2.png)

Place CB1 onto that space, make sure its direction is correct, and push gently so that its connectors fit into the slots of E3EZ. At this step, installing the motor drivers of E3EZ and the heatsink of CB1 is not necessary.

Before connecting E3EZ to USB:
- Ensure that VUSB has the jumper cap installed so that the board is powered only by USB.
- Ensure that E3EZ is in USB mode. The switch must be on the left side.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/3.png)

### Mainsail Setup
#### Writing CB1 Image on Micro SD Card
Download and install the latest [Raspberry Pi Imager](https://www.raspberrypi.com/software/ "Raspberry Pi Imager") to the computer.

Download the latest version of the system image for CB1. In this document, I used the full [Klipper kernel](https://github.com/bigtreetech/CB1/releases "CB1 Klipper Kernel").

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/4.png)

Put the micro SD card into the card reader and connect the reader to the computer.

Run the Raspberry Pi Imager.

You do not need to select anything for the “**CHOOSE DEVICE**” section.

Click the “**CHOOSE OS**” button and select the “Use Custom” option to install the Klipper image. Select the Klipper image on your computer.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/5.png)

Click the “**CHOOSE STORAGE**” button and select the micro SD card connected to the computer.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/6.png)

Click “NEXT” to proceed.

Click “YES” on the popup and start the writing process.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/7.png)

After finishing the writing and verification processes, remove the micro SD card from the reader.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/8.png)

Now, you are ready to update the **system.cfg** file.

## Connect Hermit Crab V2.0 to E3EZ
### Set CAN Bus UUID on E3EZ
Open **printer.cfg** file in Mainsail.

Write your UUID under **mcu**. In my case, the UUID is e654b29d6b66.
```
canbus_uuid: e654b29d6b66
```
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/51.png)

After you restart and reconnect to Mainsail, you will see **mcu** under the System Loads.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/52.png)

Now, you can flash Katapult and Klipper on Hermit Crab V2.0.

### Flash Katapult and Klipper on Hermit Crab V2.0
Do not connect Hermit Crab V2.0 to E3EZ yet.

#### <ins>Build Katapult</ins>
To build Katapult for Hermit Crab V2.0, first connect the board via PuTTY.\
You can find all the configs in the Hermit Crab V2.0 document.

Go to the Katapult directory to complete its menu configuration.
```
cd katapult
make menuconfig
```

Use the following config.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/53.png)

Check the file and close it by typing Q and Y.

Build Katapult.
```
make clean
make
```

#### <ins>Build Klipper</ins>
Return from the Katapult directory and go to the Klipper directory to complete its menu configuration.
```
cd ..
cd klipper
make menuconfig
```

Use the following config.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/54.png)

Check the file and close it by typing Q and Y.

Build Klipper.
```
make clean
make
```

#### <ins>Flash Katapult on Hermit Crab V2.0</ins>
Hermit Crab V2.0 has its **Boot** button on the same side as the USB-C port.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/55.png)

Hold the **Boot** button of the Hermit Crab V2.0 and connect it to E3EZ using a USB-C cable.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/56.png)

Type again `lsusb` to ensure that the CB1 is not in DFU mode.

Get the **Raspberry Pi RP2** Boot ID. In my case, it is 2e8a:0003.

Go to the Katapult directory.
```
cd ..
cd katapult
```

Flash Katapult on it.
```
make flash FLASH_DEVICE=2e8a:0003
```

Now, you can connect the Hermit Crab V2.0 to E3EZ using the CAN Bus and power them together.

#### <ins>Connect the CAN Bus</ins>
Unplug **everything**.

Connect CAN cable to Hermit Crab V2.0.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/57.png)

Connect the other end of the CAN cable to the E3EZ’s CAN slot located on the board.
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/58.png)

Power E3EZ using a micro USB power cable and wait.\
Power Hermit Crab V2.0 using a USB-C cable.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/59.png)

Open PuTTY and connect to the board.

List the devices connected to the CAN Bus.
```
python3 ~/katapult/scripts/flash_can.py -q
```
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/60.png)

Right now, you can only see the Hermit Crab V2.0’s UUID. In my case, it is 2c2ed5acf400.

Connect Mainsail and go to Devices.\
Under the Katapult title in the CAN0 tab, you should see the same UUID. If not, click the “Refresh” button.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/61.png)

Open **printer.cfg** and comment **canbus_uuid** to see Klipper and Katapult under Devices.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/62.png)

Click “Save & Restart”.

Go to Devices and click “Refresh” to see Klipper and Katapult's UUID.\
The Klipper UUID is for the E3EZ, and the Katapult UUID is for the Hermit Crab V2.0.

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/63.png)

Now, E3EZ is connected to Hermit Crab V2.0 via Katapult.

#### <ins>Flash Katapult and Klipper</ins>
Copy the Katapult UUID. In my case, it is 2c2ed5acf400.

Open PuTTY and connect to the board.

Go to the Katapult’s scripts directory.
```
cd katapult/scripts
```

Run the following command.
```
python3 flash_can.py -i can0 f ~/klipper/out/klipper.bin u 2c2ed5acf400
```
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/64.png)

You flashed the Hermit Crab V2.0 and the E3EZ with the Klipper.

Now, you can write canbus_uuid under **mcu** in the **printer.cfg** in Mainsail.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/65.png)

Click “Save & Restart”.

After you restart and reconnect to Mainsail, you will see the **mcu** details under System Loads.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/66.png)

Now, you are ready to make the hardware connection on Ender 3 Pro.

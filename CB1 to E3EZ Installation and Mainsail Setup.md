# CB1 to E3EZ Installation and Mainsail Setup
## CB1 Antenna Connection
Before installing CB1 onto E3EZ, connect its antenna.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/CB1_Antenna.png)

---

## CB1 to E3EZ Installation
E3EZ has the space to install CB1 onto the board.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/CB1_E3EZ.png)

Place CB1 onto that space, make sure its direction is correct, and push gently so that its connectors fit into the slots of E3EZ.\
At this step, installing the motor drivers of E3EZ and the heatsink of CB1 is not necessary.

\
Before connecting E3EZ to USB:
- Ensure that VUSB has the jumper cap installed so that the board is powered only by USB.
- Ensure that E3EZ is in USB mode. The switch must be on the left side.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/E3EZ_VUSB.png)

:arrow_forward: Now, you can write the CB1 image on micro SD and set Mainsail.

---

## Mainsail Setup
### Writing CB1 Image on Micro SD Card
Download and install the latest [Raspberry Pi Imager](https://www.raspberrypi.com/software/ "Raspberry Pi Imager") to the computer.

Download the latest version of the system image for CB1. In this document, I used the full [Klipper kernel](https://github.com/bigtreetech/CB1/releases "CB1 Klipper Kernel").\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/CB1_Image.png)

Put the micro SD card into the card reader and connect the reader to the computer.

Run the Raspberry Pi Imager.

You do not need to select anything for the “**CHOOSE DEVICE**” section.

Click the “**CHOOSE OS**” button and select the “**Use Custom**” option to install the Klipper image. Select the Klipper image on your computer.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/RPI_Use_Custom.png)

Click the “**CHOOSE STORAGE**” button and select the micro SD card connected to the computer.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/RPI_Choose_Storage.png)

Click “**NEXT**” to proceed.

You may have previously installed OS customization settings. You do not need to apply them, so click **“NO”**.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/RPI_Settings.png)

Click “**YES**” on the next popup and start the writing process.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/RPI_Erase.png)

After finishing the writing and verification processes, remove the micro SD card from the reader.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/RPI_Complete.png)

:arrow_forward: Now, you are ready to update the **system.cfg** file.

---

### Updating the system.cfg File
Connect the micro SD card to the card reader again.

Open the micro SD card folder and find the **system.cfg** file.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/System_Cfg.png)

Open the **system.cfg** file using *Visual Studio Code*, *Notepad++*, or a similar software.

Do the following changes in the file:
- Uncomment “Hostname” and set it. In my case, I set it as “ender3pro”.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/System_Cfg_Hostname.png)

- Uncomment “Time Zone” and set it according to your time zone. You can use [this list](https://gist.github.com/adamgen/3f2c30361296bbb45ada43d83c1ac4e5 "Time Zone List") to check your time zone.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/System_Cfg_Timezone.png)

- Enter your wifi settings next to the WIFI_SSID and WIFI_PSWD.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/System_Cfg_Wifi.png)

- Save and close the document.

:arrow_forward: Now, you can connect the micro SD card to the E3EZ board.

---

### Mainsail Update
Remove the micro SD card from the computer and put it into the E3EZ’s SOC Card slot.
Make sure that VUSB has the jumper cap installed. Later, when you connect the E3EZ to the power supply of Ender 3 Pro, you will remove that cap to prevent any damage to the board.

Power the E3EZ using USB.

Observe the 3V3 led on the E3EZ and wait a few seconds to let it boot.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/E3EZ_3V3.png)

Open the browser and enter the hostname of the E3EZ board with a “.local” suffix.\
In my case, it is http://ender3pro.local/ since my hostname is “ender3pro” in the **system.cfg** file.

It will open the Mainsail page. You can expect an error message on the Mainsail page since you need to create and set the **printer.cfg** file.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Mainsail_Error.png)

Before setting the **printer.cfg** file, do all component updates using Update Manager under the “Machine” title.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Mainsail_Update_Manager.png)

Click the refresh button to see all available component updates.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Mainsail_Updates.png)

Click the “**UPDATE ALL COMPONENTS**” button.\
A popup will appear asking for approval. Select the “I understand the risks” checkbox and click the “**START UPDATE**” button.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Mainsail_Update_All_Components.png)

It takes a while to update all components.\
After completing the updates, it disconnects and reconnects, showing the “Updating full done!” popup.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Mainsail_Update_Done.png)

:arrow_forward: Now, you can create and set the **printer.cfg** file.

---

### Create and Set the printer.cfg File
You may have a **printer.cfg** file you have created before or not have created it yet.

To check the **printer.cfg** file, open “Config Files” under the “Machine” title.\
In my case, I have created a **printer.cfg file**. You can see it in my “Config Files” folder.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Mainsail_Printer_Cfg.png)

If you have not created that file yet, follow the next steps to create an empty one.

You can create an empty **printer.cfg** file using the “Create file” button.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Mainsail_Create_Button.png)

The name of the file **MUST BE <ins>printer.cfg</ins>**.

Click **printer.cfg** file to open.

The **printer.cfg** file must have the settings to work correctly with Ender 3 Pro.

Visit this [link](https://github.com/bigtreetech/Manta-E3EZ/blob/master/Firmware/Klipper/printer-ender3.cfg "Manta E3EZ printer.cfg Settings for Ender 3") and copy the raw file. Paste it into the empty **printer.cfg** file you have created in Mainsail.

To reference all macros in the **mainsail.cfg** file, add the `[include mainsail.cfg]` line to the **printer.cfg** file.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Printer_Cfg_Include.png)

The Can BUS interface details are at the top of the file, e.g., PD12/PD13. In my case, it is PB12/PB13.\
They are important because you will use them during the CAN Bus setup.

Since we did not connect E3EZ to the printer, you can comment `(Ctrl+/)` on the following lines in the **printer.cfg** file.
- [stepper_x]\
  ![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Printer_Cfg_Stepper_X.png)

- [stepper_y]\
  ![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Printer_Cfg_Stepper_Y.png)

- [stepper_z]\
  ![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Printer_Cfg_Stepper_Z.png)

- [extruder]\
  ![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Printer_Cfg_Extruder.png)

- [heater_bed] and [fan]\
  ![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Printer_Cfg_Heater_Bed_Fan.png)

- update the [printer] lines\
  ![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/Printer_Cfg__Printer.png)

Click “**Save & Restart**”.

:arrow_forward: Now, you have created and set the **printer.cfg** file and ready to connect to CB1 with PuTTY.

---

### Connecting to CB1 with PuTTY
Install and open [PuTTY](https://www.putty.org/ "PuTTY") on your computer.

Enter the hostname of the E3EZ board with a “.local” suffix.\
In my case, it is “ender3pro.local” since my hostname is “ender3pro” in the **system.cfg** file.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/PuTTY.png)

Since CB1 installed to E3EZ runs the [image](https://github.com/bigtreetech/CB1/releases "CB1 Klipper Kernel") we installed from BIGTREETECH, you need to log in as:
>User: “biqu”\
>Password: “biqu”

![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/PuTTY_Main.png)

You can also see all the files in the device using *WinSCP*.

Enter the hostname of the E3EZ board with a “.local” suffix.\
In my case, it is “ender3pro.local” since my hostname is “ender3pro” in the **system.cfg** file.\
![](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/Images/CB1_to_E3EZ_Installation_Images/WinSCP.png)

:arrow_forward: Now, you are connected to the CB1 installed on the E3EZ from your computer and ready to set Katapult and Klipper in the next [part](https://github.com/CanBayraktarkatal/MantaE3EZ-with-CB1-and-HermitCrab2-CANBus-setup-for-Ender3Pro/blob/main/CAN%20Bus%20Setup%20on%20CB1.md "CAN Bus Setup on CB1").

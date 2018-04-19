# TinyCLR OS
---
![TinyCLR Logo](../tinyclr/images/tinyclrlogo_noborder.jpg)

TinyCLR is our own operating system and allows you to program the FEZ in C# or Visual Basic using Microsoft's Visual Studio development environment.

To start using TinyCLR with the FEZ you must first:
* Set up your computer:  Install Visual Studio, the TinyCLR OS extensions and NuGet packages.
* Set up your FEZ:  Install the GHI bootloader (if not installed already) and latest TinyCLR firmware.

## Setting Up Your Computer
Instructions for setting up your computer are found [**here**](../tinyclr/intro.md#using-tinyclr) under the TinyCLR section of our documentation.

## Setting Up Your FEZ
The following instructions explain how to install the bootloader and TinyCLR firmware on the FEZ.  The bootloader should be installed on the FEZ already.  It does not need to be reinstalled unless it accidently becomes deleted or corrupted.

The firmware may come pre-installed on the FEZ, but it might not be the latest version.  If you are having problems or just want to make sure your FEZ is up to date with the latest release, use the TinyCLR Config tool to install the latest firmware.  We have also included instructions for manually installing the firmware if that's what you prefer.

### Loading the GHI Bootloader v2
The bootloader should be installed on your FEZ already and does not need to be reinstalled unless it becomes erased or corrupted.
1. Download and save the latest [FEZCLR bootloader file](../tinyclr/loaders/ghi_bootloader.md#fezclr) (v2.x.x).
2. Download and install the [DfuSe USB device firmware upgrade software](http://www.st.com/en/development-tools/stsw-stm32080.html#getsoftware-scroll) from STMicroelectronics (click on the blue [**Get Software**](http://www.st.com/en/development-tools/stsw-stm32080.html#getsoftware-scroll) button).
3. Run the DfuSeDemo program installed in the previous step.  It should appear in the programs menu under `STMicroelectronics`.
4. On the FEZ, hold down the BOOT0 button, press and release the RESET button, and then release the BOOT0 button.  `STM Device in DFU Mode` should now appear under `Available DFU Devices` at the upper left of the DfuSe Demo program screen.
5. Near the bottom of the DfuSe Demo program window click on the `Choose...` button.  Find the bootloader file you saved in step 1 (FEZCLR Bootloader v2.x.x.dfu), click on it and click on the `Open` button.
6. Now click on the upgrade button.  If a dialog box appears with "Your device was plugged in DFU mode..." click the `Yes` button.
7. You should see a message at the bottom of the DfuSe Demo window saying the upgrade was successful.  Now reset the FEZ or click on the `Leave DFU mode` button.
8. Congratulations!  You have successfully installed the GHI bootloader!

### Loading the Firmware

> [!Tip]
> First make sure you have bootloader v2 loaded. This needs to be done only once.

#### Using TinyCLR Config
Our TinyCLR Config tool includes multiple features useful for working with TinyCLR-OS-enabled devices. It simplifies the firmware update and it includes options for accessing the TinyCLR firmware at runtime.

Using this tool is the recommended path; however, the instructions for manually loading the firmware are included below. Read more on the [TinyCLR Config](../tinyclr/tinyclr_config.md) page.

#### Manually Loading the Firmware
We recommend using the TinyCLR Config tool to update the firmware. As a backup, use these instructions:

1. Download and save the latest [FEZCLR firmware](../tinyclr/downloads.md#fezclr)
2. Put the FEZ in bootloader mode: Hold down BTN1, press and release the RESET button, and then release BTN1.
3. Open any terminal software, for example [Tera Term](http://ttssh2.osdn.jp/),
4. Select serial and pick the COM port associated with your board. (If unsure, check Device Manager)
5. Press `V` and then enter. The FEZ will respond with the installed boot loader version number (v2.x.x)
6. Press `U` and then enter to start the upload firmware procedure.
7. Press `Y` to confirm then enter. The FEZ will respond with `CCCC`...
8. Go to `File` -> `Transfer` -> `XMODEM` -> `Send` and then check the `1K` option.
9. Select the firmware file you downloaded in step 1.
10. When the transfer is complete, press the RESET button on the FEZ.

***
Check out our [**TinyCLR Tutorials**](../tinyclr/tutorials/intro.md)!

Visit our main website at [**www.ghielectronics.com**](http://www.ghielectronics.com) and our community forums at [**forums.ghielectronics.com**](https://forums.ghielectronics.com/).
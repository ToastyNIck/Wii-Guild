---
title: "BlueBomb"
---

{% include toc title="Table of Contents" %}

If you need help with anything regarding this tutorial, please join [the Wii Mini Hacking Discord server](https://discord.gg/6ryxnkS) (recommended)
{: .notice--info}

![BlueBomb](/images/bluebomb.png)

Bluebomb is an exploit made by [FullMetal5](https://github.com/Fullmetal5/bluebomb/releases) intended for Wii Mini Modding that takes advantage of an exploit in the Broadcom bluetooth stack inside the console. It's the only exploit that works on the Wii Mini but it can be used on the original Wii as well. It can also be used as brick recovery in case you haven't installed Priiloader and/or BootMii.

For the Wii U's vWii & original Wii, we recommend using [another exploit](/get-started) instead if you intend to install the Homebrew Launcher and/or BootMii
{: .notice--info}

RiiConnect24 is not available on the Wii Mini yet.
{: .notice--info}

BootMii can't be installed on the Wii Mini yet. Please don't attempt to install it. We don't take any responsibility if you brick your console. 
{: .notice--warning}

This exploit will not work on a Wii U's vWii. Please use [another exploit](/get-started).
{: .notice--warning}


#### Requirements
- A linux machine with a bluetooth adapter (an intergrated one will work)
  - If you are using a Chromebook, you do not need to install another Operating System. You can enable [Linux in ChromeOS](https://support.google.com/chromebook/answer/9145439?hl=en)
  - Using Windows Subsystem for Linux will not work, due to the inability to access `bluetoothctl`.
  - If you do not have Linux, Ubuntu is the most user-friendly option
    - 32-bit devices will require [Ubuntu 16.04](http://releases.ubuntu.com/16.04/)
    - 64-bit devices can use the [18.04 LTS version](http://releases.ubuntu.com/bionic/), but the [latest version](https://ubuntu.com/download/desktop) will work as well
- A USB flash Drive
- A Wii or Wii Mini console (obviously)

## Instructions
1. Open the Linux Terminal.
2. Disable the Bluetooth Service; `sudo systemctl disable --now bluetooth`
3. Make a new folder for Bluebomb; `mkdir bluebomb`
4. Navigate to that directory in the terminal; `cd bluebomb`
5. Download the pre-built binaries from FullMetal5's Github repo; `wget https://github.com/Fullmetal5/bluebomb/releases/download/1.5/bluebomb1.5.zip`
6. Extract the files out of the archive; `unzip bluebomb1.5.zip`
7. Plug the USB drive into your PC
8. Download the HackMii installer from [the BootMii website](https://bootmii.org/download/)
9. Extract boot.elf file from the `hackmii_installer_v1.2` folder to the USB Drive
10. Eject the USB Drive from the PC and plug it into the console
   - If you're on a normal Wii with two USB slots, plug it in the top one (or the left one if it's upright)
11. Turn the Wii on and **make sure NO Wiimotes are connected**! You can leave it on the Wii Heath and Safety Screen.
![Health and Safety Page](/images/Wii/Health_and_Safety_EN.png)
12. In the terminal, type these commands for specific Wii mini Regions: `sudo ./bluebomb [a] ./stage0/MINI_SM_[b].bin stage1.bin`
  - If you are using an external USB Bluetooth Adapter (if the PC had bluetooth built in and you wish to use an external adapter instead), replace [a] with 1, otherwise leave it blankk
  - If you use a PAL region, replace [b] with `PAL`. Likewise, if you use an NTSC console, replace [b] with `NTSC`
 

The Terminal should now display a "Waiting to accept" message. The computer is now waiting for a connection from your Wii Mini.

13. Start Pressing the `Sync` button (The Wii Mini Sync button is on the left side. On the normal Wii, it is right next to the SD card slot behind the front cover)
   - Continue Pressing until the Terminal displays "Got connection handle".

The Wii Mini should now boot to the HackMii installer (Install the Homebrew channel **only** Do **not** attempt to install BootMii)

[Continue to Homebrew Channel and BootMii Installation](hbc)
{: .notice--info}

#### cIOS Installation

This cIOS is **only** intended for use with the Wii Mini. Installing this cIOS on a normal Wii will brick your console
{: .notice--warning}
cIOS is used for USB Loaders to play backups of Wii games. Warning: this cIOS is still in experimental stage but will most likely work.
{: .notice--info}
Special thanks to Leseratte for making this ISO
{: .notice--info}

1. Download the d2xl cIOS File from https://bluebomb.glitch.me/d2xl-cIOS/index.html
1. Open the archive and drag and drop the only folder to the "apps" folder on your USB Drive 
1. Open the Homebrew Channel on your Wii Mini
1. Launch the d2x cIOS installer
1. First you gotta select which cIOS to install. in "Select cIOS", Change the value to "d2xl-v1-beta2"
1. Now Go to "Select cIOS base" and change the value to "57"
1. Now Go to "Select cIOS slot" and change the value to "249"
      Under "NOTES" there will be a section "Offline installation". Take a note of the exact version number (5 digits directly before the ".wad" extension).
1. Press A to start the installation.
       If it fails with a weird "tmd version mismatch" error, that isn't a problem. Just try again, but this time, while selecting the cIOS base, press left/right on the wiimote until the 5-digit number from earlier is different than when you tried before. This time, it should work - one of the two version numbers should definitely work.
1. After successfully installing the cIOS press B to exit. Now you have cIOS installed.

#### Enable Ethernet capability

This app will enable Ethernet functionality on your Wii Mini console. Please note that since NWFC has been discontinued you need to install [Wiimmfi](wiimmfi)
{: .notice--info}
You will need a [LAN adapter](https://www.amazon.com/Ethernet-Adapter-Switch-Wii-Nintendo-WiiU/dp/B07QPRN2VF/) and a [USB hub](https://www.amazon.co.uk/Goobay-Port-Mini-USB-2-0/dp/B005D0H0W8/) for this to work. Please note that not all USB hubs work. Please use a USB 2.0 HUB with as small power consumption as possible for the best results.
{: .notice--info}
Please note that neither CTGP nor RiiConnect24 work with the Wii Mini yet. Do **not** attempt to install either of them or you may brick your console.
{: .notice--warning}

1. Download this tool from https://bluebomb.glitch.me/wii-mini-ethernet/index.html
1. Add it to your Apps folder on your USB
1. Run it in Homebrew.
1. And you are set for life.

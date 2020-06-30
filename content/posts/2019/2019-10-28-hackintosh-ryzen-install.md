---
title: Hackintosh Ryzen Install
author: Chris Titus
type: post
date: 2019-10-29T01:13:21+00:00
url: /hackintosh-ryzen-install/
image: /wp-content/uploads/2019/10/hackintosh-Install-300x169.jpg
categories:
  - MacOS
tags:
  - Hackintosh
---
Here is the basic install instruction for the Hackintosh Ryzen install that I used on my Ryzen 2700 with an RX 580. <!--more-->

![usb-drive](https://www.christitus.com/wp-content/uploads/2019/10/usb-drive-300x230.png) 

## Download DMG File for Flash Drive

_Source Article:_ <https://forum.amd-osx.com/viewtopic.php?p=33500#p33500>

The above article is from XLNC and it goes over the creation process of the DMG file and everything he put into it. I must say he did a fantastic job with the media creation. 

Download Links from Source Article:  
CLOVER EDITION : <https://goo.gl/T3kBCN>   
ENOCH EDITION : <https://goo.gl/SVZ4ea>

Note: I used the Clover Edition and is my recommendation

## Burn DMG File with TransMac (Windows) or DD (Linux)

![transmac](https://www.christitus.com/wp-content/uploads/2019/10/transmac.jpeg) 

### TransMac Download (Windows) <https://www.acutesystems.com/scrtm.htm>

### DD (Linux)

  * Install DMG2IMG `$ sudo apt install dmg2img`
  * `$ sudo dmg2img macoshs_download.dmg macoshs_drive.iso`
  * `$ sudo dd if=macoshs_drive.iso of=/dev/sdX bs=1M`

![bios-1](https://www.christitus.com/wp-content/uploads/2019/10/bios-1.png) 

## Change Your PC&#8217;s BIOS Settings for your Hackintosh Ryzen Install

  * HPET (High Precision Timers) =Enabled
  * SATA Mode = AHCI
  * Execute Disable Bit = Enabled
  * Max CPUID Value Limit = Disabled
  * BIOS EHCI Handoff = Enabled
  * Legacy USB Support = Enabled
  * CSM (Legacy BIOS Mode) = Disabled
  * UEFI options should be enabled
  * XHCI and EHCI Hand-Off = Enabled 

![MacOSX](https://www.christitus.com/wp-content/uploads/2019/10/MacOSX-1-e1572309977936.png) 

## Insert Media and Start Installation

Boot into macOS by using the USB media. Once in the launcher start disk utility and partition the disk for macOS. 

![diskutility](https://www.christitus.com/wp-content/uploads/2019/10/diskutility.png) 

Once you have partitioned your drive, you will need to go ahead and continue the installation. Complete the installation and reboot your PC. 

Launch back into the USB Drive Installer and this time we will launch terminal. From Terminal we will run the command **XLNC**

![xlnc](https://www.christitus.com/wp-content/uploads/2019/10/xlnc.png) 

Select the following options when the XLNC installer pops up:

1. Bronya
2. Post Install
   * Type: YourDiskName
   * y to all the following questions

Reboot again, but this time when we launch the USB Menu, we will launch into the macOS we just created

Setup your Mac with your account and details

![clover](https://www.christitus.com/wp-content/uploads/2019/10/clover.png) 

Download the Clover Configurator Utility   
<https://mackie100projects.altervista.org/download-clover-configurator/>

Mount both the EFI partition from the USB and the Recovery HD

Copy the EFI Folder from the USB to the Recovery HD and then unmount both partitions and reboot your PC!

FINISHED with the Hackintosh Ryzen Install!

## Video Walkthrough
https://www.bitchute.com/video/P943EtODU3dH/

I live stream on [Twitch][1] and encourage you to drop in and ask a question. I regularly publish on [YouTube][2] and [christitus.com][3], but if you need immediate assistance, check out our discord channel at [Chris Titus Tech Discord][4].

 [1]: https://twitch.tv/christitustech
 [2]: https://www.youtube.com/c/ChrisTitusTech
 [3]: https://www.christitus.com/
 [4]: https://www.christitus.com/discord
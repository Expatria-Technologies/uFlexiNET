![Logo](/readme_images/logo_sm.jpg)
# uFlexiNET Ethernet and SD card module for FlexiHAL
<img src="/readme_images/Board_photo.jpg" width="800">


Adds Ethernet and SD card storage to a FlexiHAL CNC Controller

Currently available in our online store:

[https://expatria.myshopify.com/products/uflexinet](https://expatria.myshopify.com/products/uflexinet-ethernet-and-sd-card-module-for-flexihal)

Please consider buying a board to support our open-source designs. 

This module is designed to be installed on the 40 pin GPIO header of the FlexiHAL CNC controller.  It adds a uSD card interface and an Ethernet interface to the platform.  This brings compatbility with the SD card and Networking plugins with GRBLHAL.  Notably, this allows the use of named files for subroutines, probing routines and automatic toolchanging functions in GRBLHAL.  In addition, the module allows the user to connect compatible senders via Websockets (recomended) or Telnet.  The MQTT plugin can also be used if custom plugin code is written.

Remora and LinuxCNC support via Ethernet is still being tested and the release is not ready to be published.  To use Remora with this module, users are responsible for researching and compiling their own components.

Optimized GRBLHAL driver is located here.  Look for releases with "ETH" in the name to use this module: 
https://github.com/Expatria-Technologies/STM32F4xx/releases

### Installation
<img src="/readme_images/Board_installed.jpg" width="800">

Disconnect power to the FlexiHAL and install the module in the GPIO header as shown above.  Be aware of excess cable strain (especially with heavy shielded CAT6 Ethernet cables and install spacers, fasteners and strain relief as needed.  If installing an SD card it is recommended to insert it before attaching the uFlexiNET to the mainboard as it is easier to ensure that it has the correct orientation.  Ensure the SD card is formatted as FAT32 and subsequent file operations (upload, delete) can be done via FTP over Ethernet or via the Ymodem protocol in senders like IOSender.

Note that the MCU on Flexi still needs 5V power supplied.  Normally this is via the USBC connector but it is also possible to jumper the 5V bypass pins on flexi to use the onboard 5V regulator.  Please note that this bypasses the galvanic isolation of FLexi and is not generally recommended.  See the FlexiHAL Readme for details:
https://github.com/Expatria-Technologies/Flexi-HAL#power-input



### Usage

Ensure that you flash appropriate GRBLHAL or Remora firmware to your FlexiHAL after installation.  See GRBLHAL and Remora documentation for further usage examples.  

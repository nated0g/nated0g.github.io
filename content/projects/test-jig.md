---
title: "openGRO v1.0"
date: 2013-12-02T00:00:00-08:00
draft: false
image: cm-testjig.jpg
tags: ["Hardware", "Firmware", "CAD"]
---
Testing and commissioning device for Canopy Mate control hardware.
<!--more-->
Canopy Mate is an automated cannabis grow tent.  I designed the PCB for it, and 
collaborated on the firmware and app development.

My favourite part of that project though, was this test-jig I made.  I designed
and 3d printed the housing, which includes an array of pogo-pins that align
with test pads I designed in to the PCB.  The pogo pins connect to
opto-isolated inputs on a Raspberry Pi 4 which runs the testing software.

I wrote the testing software in Python, with a Tkinter GUI.  It first flashes a 
test firmware onto the device, which communicates with the test-jig over UART.
All inputs and outputs are tested, and after passing, production firmware is
flashed to the device.  The device is also commissioned with Google Cloud IoT,
and unique credentials are generated for the AP for initial device setup.

All details of the test are stored in a database, and a pair of labels including
the device serial number, SSID and credentials are printed via a label printer 
connected to the Pi.  

Overall the test-jig massively increased production efficiency, and reduced 
change for human error.

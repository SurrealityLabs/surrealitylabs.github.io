---
id: 264
title: NESVerter
date: 2013-06-09T02:11:36+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=264
permalink: /2013/06/nesverter/
categories:
  - Project Updates
tags:
  - NESVerter
---
<h2>Introduction</h2>
The NESVerter is a conversion board to make an original NES controller into a USB gamepad. It originally came about after I made one based on <a href='http://www.raphnet.net/electronique/snes_nes_usb/index_en.php'>this one over on raphnet.net</a> for my friend Kat. I wanted to try making a PIC-based version that would fit inside an NES controller without modification to the case. This is the result.

The NESVerter is a small PIC18F14K50-based board that solders into an NES controller in place of the standard 4021 shift register. It requires removing that part. For more on how the NES controller works, visit <a href='http://www.diylive.net/index.php/2006/02/03/decoding-nes-controller/' target='_blank'>here.</a>

<h2>Hardware</h2>
There are two versions of the hardware, mostly the same. Version 1 is a slightly larger board, with a reset and a bootloader button so you can download new code to the board. Due to a miscalculation on my part, Version 1 requires filing down part of the case. Version 2 is smaller (thus no filing) and loses the buttons in favour of using the controller's buttons on power up to activate the bootloader.

<a href="http://www.flickr.com/photos/61091961@N06/8964803744/" title="NESVerter versions 1 and 2" rel="lightbox" target="_blank"><img src="http://farm4.staticflickr.com/3693/8964803744_ee478e8e68_n.jpg" width="320" height="240" alt="NESVerter versions 1 and 2" title="NESVerter versions 1 and 2" class="aligncenter"></a>

The schematics are as follows:

<a href="http://www.flickr.com/photos/61091961@N06/8958138349/" title="NESVerter 1.0 Schematic" rel="lightbox" target="_blank"><img src="http://farm8.staticflickr.com/7361/8958138349_6f16a0b53a.jpg" width="500" height="373" alt="NESVerter 1.0 Schematic" title="NESVerter 1.0 Schematic" class="aligncenter"></a>

<a href="http://www.flickr.com/photos/61091961@N06/8959343476/" title="NESVerter 2.0 Schematic" rel="lightbox" target="_blank"><img src="http://farm9.staticflickr.com/8540/8959343476_5b36598950.jpg" width="500" height="373" alt="NESVerter 2.0 Schematic" title="NESVerter 2.0 Schematic" class="aligncenter"></a>

This is a very, very basic USB PIC setup. There are some pads for ICSP and USB connections, a couple of capacitors for the PIC, a crystal and load caps, pullup resistor on reset, and the 330nF capacitor on the VUSB pin. The 4021 is only used in the schematic as a footprint - it's actually populated as pins connecting the board in place of the removed 4021 in the NES controller. Pullup / pulldown resistors on the inputs aren't required, as they're in place on the controller PCB (as printed-on carbon).

<h2>Firmware</h2>
The firmware can be downloaded at our Bitbucket site <a href='http://code.surrealitylabs.com/nesverter/' target='_blank'>here.</a> It's based on <a href='http://code.google.com/p/jallib/' target='_blank'>JALv2 with JALLIB</a>. HEX files are also included. The first versions were based on Microchip USB stack examples, but licensing issues with those led me down the JAL route, which actually turned out well.

There are actually two parts to the firmware. The first is the USB HID bootloader, which allows you to download updated code to the controller without taking it apart and breaking out the PICKit2. There are two versions - one for the V1 hardware and one for the V2. The V1 one uses the buttons on the PCB, while the V2 requires that you hold down the A and B buttons on the controller while plugging it in to enter the bootloader. I think the V2 one will work on the V1 hardware, so just use that. The bootloader gets loaded on via the ICSP board and something like a PICKit2.

The second part of the firmware is the actual gamepad firmware, which you load on via the bootloader. This is a very basic USB Gamepad firmware. I copied the USB descriptor from <a href='http://www.raphnet.net/electronique/snes_nes_usb/index_en.php' target='_blank'>raphnet's version</a>, and much of the rest of the code comes from <a href='http://jallib.blogspot.ca/2009/07/pic-18f14k50-usb-interface-board-part-3.html' target='_blank'>this JALLIB sample</a>. All it really does is check which buttons are pushed, and sets the appropriate bits in the USB HID report for those buttons. That's it. The code is documented if you want to have a look.

<h2>Building it</h2>
The board is all-SMD, and fairly tiny stuff too. I'm only providing instructions and a parts list for Version 2, as I don't recommend building Version 1. You'll need the following parts:
<table border="0" cellpadding="3" cellspacing="3">
<thead>
<tr>
<th style="padding-left: 6px; padding-right: 6px;">Device</th>
<th style="padding-left: 6px; padding-right: 6px;">Quantity</th>
<th style="padding-left: 6px; padding-right: 6px;">Parts on board</th>
<th style="padding-left: 6px; padding-right: 6px;">Digi-key part number</th>
</tr>
</thead>
<tbody>
<tr>
<td>10K 0603 resistor</td>
<td>1</td>
<td>R1</td>
<td>311-10KGRCT-ND</td>
</tr>
<tr>
<td>10uF 0805 capacitor</td>
<td>1</td>
<td>C3</td>
<td>445-1371-1-ND</td>
</tr>
<tr>
<td>12.000 MHz Crystal, 5x3.2mm</td>
<td>1</td>
<td>Q1</td>
<td>535-10875-1-ND</td>
</tr>
<tr>
<td>22pF 0603 capacitor</td>
<td>2</td>
<td>C4, C5</td>
<td>445-1273-1-ND</td>
</tr>
<tr>
<td>100nF 0603 capacitor</td>
<td>1</td>
<td>C1</td>
<td>311-1343-1-ND</td>
</tr>
<tr>
<td>330nF 0603 capacitor</td>
<td>1</td>
<td>C2</td>
<td>445-5142-1-ND</td>
</tr>
<tr>
<td>PIC18F14K50, SSOP package</td>
<td>1</td>
<td>IC2</td>
<td>PIC18F14K50-I/SS-ND</td>
</tr>
</tbody>
</table>


Note the thickness of the PCB - using standard 1.6mm PCBs is a bad idea here. Pay a little extra for thin, if you have to - I went with 0.8mm.

I won't cover how to build the board - if you're experienced with surface-mount soldering, odds are you can figure out where stuff goes based on the parts list above and the silkscreen on the board. You will need to burn the bootloader to the board, however. For that, I use a PICKit2 with a cable and pogopins. The same pads that are used for USB can be used for ICSP to load the bootloader - connection is as follows:

<a href="http://www.flickr.com/photos/61091961@N06/8992594467/" title="NESVerter ICSP pinout" rel="lightbox" target="_blank"><img src="http://farm6.staticflickr.com/5444/8992594467_dd14931146_m.jpg" width="240" height="159" alt="NESVerter ICSP pinout" title="NESVerter ICSP pinout"></a>

Here's how to assemble the controller:
<ol>
<li>Get an NES controller</li>
<li>Open the controller, and remove the board from the case
<a href="http://www.flickr.com/photos/61091961@N06/8965667744/" title="Step 1: Open the controller" rel="lightbox" target="_blank"><img src="http://farm8.staticflickr.com/7435/8965667744_6a78fce900_m.jpg" width="240" height="180" alt="Step 1: Open the controller" title="Step 1: Open the controller" class="aligncenter"></a><a href="http://www.flickr.com/photos/61091961@N06/8965700300/" title="Step 2: Remove the circuit board" rel="lightbox" target="_blank"><img src="http://farm3.staticflickr.com/2825/8965700300_2b2900cd71_m.jpg" width="240" height="180" alt="Step 2: Remove the circuit board" title="Step 2: Remove the circuit board" class="aligncenter"></a>
<li>Desolder the cable
<a href="http://www.flickr.com/photos/61091961@N06/8965702022/" title="Step 3: Desolder the cable" rel="lightbox" target="_blank"><img src="http://farm8.staticflickr.com/7306/8965702022_f5c362bd68_m.jpg" width="240" height="180" alt="Step 3: Desolder the cable" title="Step 3: Desolder the cable"></a></li>
<li>Desolder the 4021 chip
<a href="http://www.flickr.com/photos/61091961@N06/8964530465/" title="Step 4: Desolder the 4021 chip" rel="lightbox" target="_blank"><img src="http://farm9.staticflickr.com/8280/8964530465_f4a606a147_m.jpg" width="240" height="180" alt="Step 4: Desolder the 4021 chip" title="Step 4: Desolder the 4021 chip"></a><a href="http://www.flickr.com/photos/61091961@N06/8964531865/" title="Step 5: Pry off the desoldered chip" rel="lightbox" target="_blank"><img src="http://farm3.staticflickr.com/2849/8964531865_6e3b92a339_m.jpg" width="240" height="180" alt="Step 5: Pry off the desoldered chip" title="Step 5: Pry off the desoldered chip"></a></li>
<li>Line up the NESVerter over the IC holes
<a href="http://www.flickr.com/photos/61091961@N06/8965725204/" title="Step 6: Line up the NESVerter board" rel="lightbox" target="_blank"><img src="http://farm9.staticflickr.com/8404/8965725204_ee01274c8a_m.jpg" width="240" height="180" alt="Step 6: Line up the NESVerter board" title="Step 6: Line up the NESVerter board"></a></li>
<li>Thread small-gauge wire through the holes, and solder on both sides. Then, clip the wires.
<a href="http://www.flickr.com/photos/61091961@N06/8965759122/" title="Step 7: Add wires" rel="lightbox" target="_blank"><img src="http://farm4.staticflickr.com/3771/8965759122_5ca996f462_m.jpg" width="240" height="180" alt="Step 7: Add wires" title="Step 7: Add wires"></a><a href="http://www.flickr.com/photos/61091961@N06/8965790020/" title="Step 8: Solder the wires" rel="lightbox" target="_blank"><img src="http://farm3.staticflickr.com/2869/8965790020_4f0fd4211f_m.jpg" width="240" height="180" alt="Step 8: Solder the wires" title="Step 8: Solder the wires"></a><a href="http://www.flickr.com/photos/61091961@N06/8965792152/" title="Step 8: Soldering" rel="lightbox" target="_blank"><img src="http://farm3.staticflickr.com/2893/8965792152_7e3976d8d5_m.jpg" width="240" height="180" alt="Step 8: Soldering" title="Step 8: Soldering"></a><a href="http://www.flickr.com/photos/61091961@N06/8964601777/" title="Step 9: Cut the wires" rel="lightbox" target="_blank"><img src="http://farm6.staticflickr.com/5461/8964601777_39e630da97_m.jpg" width="240" height="180" alt="Step 9: Cut the wires" title="Step 9: Cut the wires"></a></li>
<li>Cut the end off the USB cable (the PROPER end - not the type A plug!). Strip and tin the wires.
<a href="http://www.flickr.com/photos/61091961@N06/8964602963/" title="Step 10: Grab a USB cable" rel="lightbox" target="_blank"><img src="http://farm9.staticflickr.com/8126/8964602963_8c369444ca_m.jpg" width="240" height="180" alt="Step 10: Grab a USB cable" title="Step 10: Grab a USB cable"></a><a href="http://www.flickr.com/photos/61091961@N06/8965796352/" title="Step 11: Cut off the square end" rel="lightbox" target="_blank"><img src="http://farm6.staticflickr.com/5338/8965796352_2deacb2de4_m.jpg" width="240" height="180" alt="Step 11: Cut off the square end" title="Step 11: Cut off the square end"></a><a href="http://www.flickr.com/photos/61091961@N06/8964605665/" title="Step 12: Strip off the plastic" rel="lightbox" target="_blank"><img src="http://farm8.staticflickr.com/7399/8964605665_892957d76e_m.jpg" width="240" height="180" alt="Step 12: Strip off the plastic" title="Step 12: Strip off the plastic"></a><a href="http://www.flickr.com/photos/61091961@N06/8965804056/" title="Step 13: Strip and tin the wires" rel="lightbox" target="_blank"><img src="http://farm4.staticflickr.com/3744/8965804056_f32e544bda_m.jpg" width="240" height="180" alt="Step 13: Strip and tin the wires" title="Step 13: Strip and tin the wires"></a></li>
<li>Solder the wires to the PCB. The pads are indicated with the colour of the wire (G = Green, W = White, R = Red, B = Black) that attaches to them.
<a href="http://www.flickr.com/photos/61091961@N06/8964620489/" title="Step 14: Solder to the PCB" rel="lightbox" target="_blank"><img src="http://farm3.staticflickr.com/2837/8964620489_5e3efabc91_m.jpg" width="240" height="180" alt="Step 14: Solder to the PCB" title="Step 14: Solder to the PCB"></a></li>
<li>Route the USB cable, and reassemble the controller
<a href="http://www.flickr.com/photos/61091961@N06/8965901580/" title="Step 15: Start reassembly" rel="lightbox" target="_blank"><img src="http://farm9.staticflickr.com/8406/8965901580_56599e3917_m.jpg" width="240" height="180" alt="Step 15: Start reassembly" title="Step 15: Start reassembly"></a><a href="http://www.flickr.com/photos/61091961@N06/8965914454/" title="Step 16: Put the buttons back in" rel="lightbox" target="_blank"><img src="http://farm4.staticflickr.com/3707/8965914454_63c148860f_m.jpg" width="240" height="180" alt="Step 16: Put the buttons back in" title="Step 16: Put the buttons back in"></a><a href="http://www.flickr.com/photos/61091961@N06/8964726727/" title="Step 17: Put in the PCB assembly" rel="lightbox" target="_blank"><img src="http://farm8.staticflickr.com/7435/8964726727_737bbc9eeb_m.jpg" width="240" height="180" alt="Step 17: Put in the PCB assembly" title="Step 17: Put in the PCB assembly"></a><a href="http://www.flickr.com/photos/61091961@N06/8964761027/" title="Step 18: Route the USB cable" rel="lightbox" target="_blank"><img src="http://farm4.staticflickr.com/3800/8964761027_ae552a8e13_m.jpg" width="240" height="180" alt="Step 18: Route the USB cable" title="Step 18: Route the USB cable"></a><a href="http://www.flickr.com/photos/61091961@N06/8964762123/" title="Step 19: Put the back back on" rel="lightbox" target="_blank"><img src="http://farm8.staticflickr.com/7289/8964762123_35f81c91b6_m.jpg" width="240" height="180" alt="Step 19: Put the back back on" title="Step 19: Put the back back on"></a><a href="http://www.flickr.com/photos/61091961@N06/8965960534/" title="Step 20: Done!" rel="lightbox" target="_blank"><img src="http://farm6.staticflickr.com/5453/8965960534_5cecda5e40_m.jpg" width="240" height="180" alt="Step 20: Done!" title="Step 20: Done!"></a></li>
</ol>

<h2>Loading the firmware, and testing it</h2>
To load the firmware, you'll need to use the USB HID Bootloader program that comes with the <a href='http://www.microchip.com/mla/'>Microchip Libraries for Applications</a>. The program is in the USB\Device - Bootloaders\HID directory. Follow the following steps:
<ol>
<li>Open the program</li>
<li>Hold down the A and B buttons on the controller (for the V2 bootloader) or press the bootloader button (for the V1 bootloader) and plug in the controller</li>
<li>The app should indicate that the device was found.</li>
<li>Click the Open button, and open the nesverter.hex file from the code-gamepad directory in the source code download</li>
<li>Click the Erase/Program/Verify button to download the code</li>
<li>When the app tells you, unplug the controller and plug it back in.</li>
</ol>
To test it, you'll need an app to test the controller. On a Mac, I use Joystick Show from the Mac App Store. On Windows, you can go into Devices, right click on NESVerter, go to Game Device Properties, click on NESVerter and hit Properties. That'll show you the state of each button.

<h2>Using it</h2>
The gamepad is a standard USB HID gamepad, so it'll work on any major modern OS without a custom driver. You'll need to consult the documentation for whatever game, emulator, etc. you're using to see what, if any, configuration it needs to use a standard gamepad. Some emulators on the Mac, for example, require the Emulator Enhancer program to use a gamepad.

<h2>Lessons learned, and conclusions</h2>
Overall, this project was a big success - the system worked very well for bringing the venerable NES controller into more modern times, and was a very inexpensive way to do so. The first version had issues requiring a little filing of the case to fit the board, but that was easily corrected in version 2. Definitely something to keep track of in future versions - making sure the dimensions are correct before sending boards out for manufacture.

In future, I'd like to do another version of this - without surface mount or stitching together boards, both of which are difficult for people who aren't that experienced with soldering. I'm thinking of doing one with through-hole parts and Microchip's newer (and cheaper) USB parts, with a full-PCB replacement for the NES controller. Before I do so, though, I'll have to find some more NES controllers - they're getting harder to come by.
---
id: 435
title: 'USB Wildcard: Open Hardware Advent Calendar Day 5'
date: 2014-12-05T21:41:16+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=435
permalink: /2014/12/usb-wildcard-open-hardware-advent-calendar-day-5/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
gallery:
  - url: /assets/images/projects/usb-wildcard/photos/usb-wildcard-top.jpg
    image_path: /assets/images/projects/usb-wildcard/thumbnails/usb-wildcard-top.jpg
    alt: "USB Wildcard, from above"
    title: "USB Wildcard, from above"
  - url: /assets/images/projects/usb-wildcard/photos/usb-wildcard-bottom.jpg
    image_path: /assets/images/projects/usb-wildcard/thumbnails/usb-wildcard-bottom.jpg
    alt: "USB Wildcard, from below"
    title: "USB Wildcard, from below"
  - url: /assets/images/projects/usb-wildcard/photos/usb-wildcard-panel.jpg
    image_path: /assets/images/projects/usb-wildcard/thumbnails/usb-wildcard-panel.jpg
    alt: "USB Wildcard boards in a panel"
    title: "USB Wildcard boards in a panel"
gallery2:
  - url: /assets/images/projects/usb-wildcard/schematic.png
    image_path: /assets/images/projects/usb-wildcard/schematic-thumb.png
    alt: "Schematic"
    title: "Schematic"
---
Today's project is more of a tool that I'll be using in future projects: what I call the USB Wildcard.

<h2>Overview</h2>
The USB Wildcard is a basic breakout board for developing USB systems using AVR microcontrollers. It's basically the USB to Serial section of an Arduino Uno, but on its own circuit board.

{% include gallery id="gallery" %}

The main configuration for this board is as a USB to Serial adapter for my own Arduino experiments, but the back has pads for connecting to the other I/O lines on the ATmega16U2 chip on the board.

<h2>Hardware</h2>
The board is a double-sided PCB with parts only on the top side. It's a really basic setup - the microcontroller, some capacitors, the crystal, a handful of LEDs, and a USB connector.

{% include gallery id="gallery2" %}

The schematic and PCB files can be <a href="https://github.com/SurrealityLabs/USBWildcard" target="_blank">downloaded from our GitHub</a>. This includes a version of the board that merges two of the boards into one, so you can get 20 boards from an order of 10 5x5cm boards.

<h2>Software setup</h2>
The software for this one is really basic so far. For the USB to Serial board, I use the Arduino Uno HEX file, so it looks exactly like an Arduino Uno's serial port to the computer. The hex file can be download from <a href="https://github.com/arduino/Arduino/blob/master/hardware/arduino/firmwares/atmegaxxu2/arduino-usbserial/Arduino-usbserial-atmega16u2-Uno-Rev3.hex" target="_blank">here.</a>

To load the firmware, you either need FLIP (Windows) or dfu-programmer (Linux and OS X). Instructions <a href="http://arduino.cc/en/Hacking/DFUProgramming8U2" target="_blank">can be found on the Arduino site here</a>, but the basic steps for programming the board on a Mac or Linux machine are to plug the blank board into the computer, and run the following from the command line:

sudo dfu-programmer atmega16u2 erase --force
sudo dfu-programmer atmega16u2 flash Arduino-usbserial-atmega16u2-Uno-Rev3.hex
sudo dfu-programmer atmega16u2 reset

Unplug it, plug it back in, and you've got a USB to Serial adapter.

Future projects will expand on this one, and present some more detailed usage instructions.

<h2>Future plans</h2>
This is the basis of a few future projects, as it gives us an easy, pre-made platform for building USB gadgets. I have a lot of plans for it, is what I'm trying to say.

<h2>Conclusion</h2>
This isn't the best writeup of this project - I'm writing it on the way to a concert, so I'm rushing it - but the details will be filled in later.
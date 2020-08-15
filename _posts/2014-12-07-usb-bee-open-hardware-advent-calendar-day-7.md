---
id: 440
title: 'USB Bee: Open Hardware Advent Calendar Day 7'
date: 2014-12-07T21:23:30+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=440
permalink: /2014/12/usb-bee-open-hardware-advent-calendar-day-7/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
gallery:
  - url: /assets/images/projects/usbbee/photos/usbbee-on-board.jpg
    image_path: /assets/images/projects/usbbee/thumbnails/usbbee-on-board.jpg
    alt: "USBBee, on a board"
    title: "USBBee, on a board"
  - url: /assets/images/projects/usbbee/photos/usbbee-top.jpg
    image_path: /assets/images/projects/usbbee/thumbnails/usbbee-top.jpg
    alt: "USBBee, from above"
    title: "USBBee, from above"
gallery2:
  - url: /assets/images/projects/usbbee/schematic.png
    image_path: /assets/images/projects/usbbee/schematic-thumb.png
    alt: "Schematic"
    title: "Schematic"
---
Today's project is a handy little board for working with Arduino projects that use XBee radios.

<h2>Overview</h2>
The USB Bee is a small circuit board that can take the place of an XBee radio, but rather than having a wireless communications module, it has a USB port.

{% include gallery id="gallery" %}

<a href="https://www.sparkfun.com/pages/xbee_guide" target="_blank">XBee radios</a> are often used as a serial data link, with another radio connected to a computer. In the field, this is awesome. In the lab or on the workbench, it can be a bit of a pain - especially when you design the board to leave out the Arduino serial programming interface to save space, and only have the connection to the radio module. As I have done.

By putting the USB to Serial module in the same size module as the radio, we can leave just the radio connector on the board, and save some space - just swap in the USB Bee when you need a direct connection, and put the XBee back when you're done.

<h2>Hardware</h2>
The system is a very basic FT232RL-based USB to Serial converter, using a Micro USB connector and a thin PCB to match the XBee radios. It has two solder jumpers to select if the board is simulating an XBee, or connecting to an XBee - so it can be used either to replace the radio in the system, or to connect to the radio on a computer.

{% include gallery id="gallery2" %}

The I/O on this board runs at 3.3V, just like a normal XBee module. PCB designs and schematic can be downloaded from <a href="https://github.com/SurrealityLabs/USBBee" target="_blank">our GitHub page</a>.

<h2>Future enhancements</h2>
Already, the design has had one minor modification - I got RX and TX backwards. Switching some labels and connections fixed this easily in version 1.1. I'd like to add a voltage regulator to power the XBee's 3.3V supply, as well, so that it can actually be used as an interface to connect an XBee to USB.

<h2>Conclusion</h2>
I don't think this is a board that anyone but me would have had a need to build - most people just leave an FTDI serial header on the board so they can program it, but I didn't. Still, it solves the need nicely, and might be useful for people developing systems with XBees in environments where there's too much interference to test.
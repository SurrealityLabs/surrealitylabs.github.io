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
---
Today's project is a handy little board for working with Arduino projects that use XBee radios.

<h1>Overview</h1>
The USB Bee is a small circuit board that can take the place of an XBee radio, but rather than having a wireless communications module, it has a USB port.

[AFG_gallery id='21']

<a href="https://www.sparkfun.com/pages/xbee_guide" target="_blank">XBee radios</a> are often used as a serial data link, with another radio connected to a computer. In the field, this is awesome. In the lab or on the workbench, it can be a bit of a pain - especially when you design the board to leave out the Arduino serial programming interface to save space, and only have the connection to the radio module. As I have done.

By putting the USB to Serial module in the same size module as the radio, we can leave just the radio connector on the board, and save some space - just swap in the USB Bee when you need a direct connection, and put the XBee back when you're done.

<h1>Hardware</h1>
The system is a very basic FT232RL-based USB to Serial converter, using a Micro USB connector and a thin PCB to match the XBee radios. It has two solder jumpers to select if the board is simulating an XBee, or connecting to an XBee - so it can be used either to replace the radio in the system, or to connect to the radio on a computer.

<a href="http://www.flickr.com/photos/61091961@N06/15970493665/" title="usbbee-r1" rel="lightbox"><img src="http://farm8.staticflickr.com/7550/15970493665_974b02cf39_n.jpg" width="320" height="239" alt="usbbee-r1" title="usbbee-r1" class="aligncenter"></a>

The I/O on this board runs at 3.3V, just like a normal XBee module. PCB designs and schematic can be downloaded from <a href="https://github.com/SurrealityLabs/USBBee" target="_blank">our GitHub page</a>.

<h1>Future enhancements</h1>
Already, the design has had one minor modification - I got RX and TX backwards. Switching some labels and connections fixed this easily in version 1.1. I'd like to add a voltage regulator to power the XBee's 3.3V supply, as well, so that it can actually be used as an interface to connect an XBee to USB.

<h1>Conclusion</h1>
I don't think this is a board that anyone but me would have had a need to build - most people just leave an FTDI serial header on the board so they can program it, but I didn't. Still, it solves the need nicely, and might be useful for people developing systems with XBees in environments where there's too much interference to test.
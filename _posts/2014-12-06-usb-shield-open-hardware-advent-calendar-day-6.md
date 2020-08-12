---
id: 438
title: 'USB Shield: Open Hardware Advent Calendar Day 6'
date: 2014-12-06T22:06:14+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=438
permalink: /2014/12/usb-shield-open-hardware-advent-calendar-day-6/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
---
Today's project is a safety device to protect against malicious USB charging ports. We're calling it the USB Shield.

<h1>Overview</h1>
The USB Shield is a device to protect against malicious USB charging ports. Essentially, USB charging ports in places like airports and bus terminals aren't supposed to be connected to computers, but if they are, and you plug your phone or tablet into them, they could seize control of your device and install nasty software on it. By breaking the data connection between the device and the port, the USB Shield prevents this from happening.

[AFG_gallery id='20']

Other devices have been designed for this - a few have made it to Kickstarter - but I wanted a small one for very little money. So I built my own.

<h1>Hardware</h1>
The hardware design is very simple. We've got a USB socket and a USB plug, with the power and ground connected between them. The data lines on the socket are connected to a switch. For Android devices, the data lines are connected together, making the port a Dedicated Charger Port. For iOS devices, the data lines are connected to a pair of voltage dividers. The resistors are selected to limit the charging current to 500mA so as to not overload the charger.

<a href="http://www.flickr.com/photos/61091961@N06/15962967962/" title="usbshield-r1" rel="lightbox"><img src="http://farm9.staticflickr.com/8566/15962967962_3a82e24253_n.jpg" width="320" height="239" alt="usbshield-r1" title="usbshield-r1" class="aligncenter"></a>

The PCB design files can be found <a href="https://github.com/SurrealityLabs/USBShield/" target="_blank">at our GitHub site</a>.

Building one isn't too difficult - the hardest part is installing the four resistors (two 49.9K ohm 0603 resistors and two 75K ohm 0603 resistors), because they're surface mount. The USB connectors and switch are easy to install.

<h1>Future improvements</h1>
There is one issue with the board as is - the Dedicated Charging Port is meant as a 1A charge limit, and I'd prefer to have it limited to 500mA for safety reasons. There are also no mounting holes on the board, which makes it more difficult to mount it in an enclosure. I'm working on a new version that addresses both issues, but the existing one does work.

<h1>Conclusion</h1>
If you're going to use charging ports in public places, it's probably a good idea to use something like this to keep your mobile device safe.
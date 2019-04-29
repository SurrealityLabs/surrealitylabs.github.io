---
id: 465
title: 'Pinbox: Open Hardware Advent Calendar Day 16'
date: 2014-12-16T23:41:10+00:00
guid: http://surrealitylabs.com/?p=465
permalink: /2014/12/pinbox-open-hardware-advent-calendar-day-16/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
gallery:
  - url: /assets/images/projects/pinbox/photos/pinbox-pcb.jpg
    image_path: /assets/images/projects/pinbox/thumbnails/pinbox-pcb.jpg
    alt: "Pinbox PCB"
    title: "Pinbox PCB"
  - url: /assets/images/projects/pinbox/photos/pinbox-buttons.jpg
    image_path: /assets/images/projects/pinbox/thumbnails/pinbox-buttons.jpg
    alt: "Pinbox PCB with buttons"
    title: "Pinbox PCB with buttons"
gallery2:
  - url: /assets/images/projects/pinbox/schematic.png
    image_path: /assets/images/projects/pinbox/schematic-thumb.png
    alt: "Schematic"
    title: "Schematic"
---
This one's another project in progress - a controller for playing PC-based pinball.

<h2>Overview</h2>
Recently, we started playing Pinball Arcade - a really nice pinball simulator. As some of the people behind DIYPinball, naturally we find virtual pinball games to be lacking, but you can't always take a pinball machine with you.

{% include gallery id="gallery" %}

Enter the Pinbox: a custom controller for playing pinball on a computer. Rather than using your shift keys and spacebar, you get actual arcade buttons on the sides of a box, and a plunger. Or at least you will when we finish it.

<h2>Hardware</h2>
The circuit is basically an Arduino Leonardo on a 5cm x 5cm circuit board. An ATMega32U4 is the brain, and it has five inputs for buttons - two flippers both left and right, and a start button - and an input for a <a href="https://www.sparkfun.com/products/9322" target="_blank">SparkFun photointerrupter board</a>. It also has a header for installing an eventual accelerometer module for tilt detection.

{% include gallery id="gallery2" %}

Schematic and PCB files can be <a href="https://github.com/SurrealityLabs/Pinbox" target="_blank">downloaded from our GitHub</a>.

<h2>Software</h2>
The software is still in progress. The basic function is to act as a USB keyboard, activating the shift keys for the flipper buttons, the Return key for the start button, and the spacebar for the plunger. It uses some debouncing using the Bounce library to take care of the button inputs. Eventually the software will be expanded to interface with the accelerometer to allow you to bump and tilt the table. We use the Leonardo's built-in Keyboard library to handle sending keypresses to the computer.

Before loading the code, the AVR on the Pinbox board needs to be loaded with the Caterina bootloader. This is done by connecting an AVR programmer to JP1 - I use a USBTinyISP - and using Tools -> Burn Bootloader. From then on, the board can be programmed over USB, just like an Arduino Leonardo.

Source code can be <a href="https://github.com/SurrealityLabs/Pinbox" target="_blank">downloaded from our GitHub</a>.

<h2>Future plans</h2>
This one's still a work in progress. We still need to figure out the plunger mechanism, using the optical sensor and a knob of some sort. After that, we need to mount it in a box - and then, we need to hook up the accelerometer. So there's plenty to do, but a clear path to the finish.
---
id: 462
title: 'Spherebot Controller: Open Hardware Advent Calendar Day 15'
date: 2014-12-15T23:55:47+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=462
permalink: /2014/12/spherebot-controller-open-hardware-advent-calendar-day-15/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
gallery:
  - url: /assets/images/projects/spherebot-controller/photos/spherebot-1.jpg
    image_path: /assets/images/projects/spherebot-controller/thumbnails/spherebot-1.jpg
    alt: "Spherebot PCB with motor drivers"
    title: "Spherebot PCB with motor drivers"
  - url: /assets/images/projects/spherebot-controller/photos/spherebot-2.jpg
    image_path: /assets/images/projects/spherebot-controller/thumbnails/spherebot-2.jpg
    alt: "Spherebot PCB with motor drivers"
    title: "Spherebot PCB with motor drivers"
  - url: /assets/images/projects/spherebot-controller/photos/spherebot-back.jpg
    image_path: /assets/images/projects/spherebot-controller/thumbnails/spherebot-back.jpg
    alt: "Back of Spherebot PCB"
    title: "Back of Spherebot PCB"
  - url: /assets/images/projects/spherebot-controller/photos/spherebot.jpg
    image_path: /assets/images/projects/spherebot-controller/thumbnails/spherebot.jpg
    alt: "Spherebot"
    title: "Spherebot"
gallery2:
  - url: /assets/images/projects/spherebot-controller/schematic.png
    image_path: /assets/images/projects/spherebot-controller/schematic-thumb.png
    alt: "Schematic"
    title: "Schematic"
---
Today's entry isn't quite done yet, but that's only because I completely blanked on getting the rest of the parts when I was at the store on Saturday. Oops.

It's a controller board for the Spherebot.

<h2>Overview</h2>
The <a href="http://pleasantsoftware.com/developer/3d/spherebot/" target="_blank">Spherebot</a> is an alternative design to <a href="http://egg-bot.com/" target="_blank">EMSL's EggBot</a>. It's meant to be cheaper, maybe a bit more hackable, and perhaps <a href="http://www.thingiverse.com/thing:7656" target="_blank">made out of 3D printed parts</a>.

I want to take this opportunity right off the top: if you've got the resources, I highly suggest buying one of EMSL's offerings. They're open-source, and very well designed and made. EMSL do VERY good work.

We, however, didn't want to spend a ton for screwing around with drawing on ping pong balls, and wanted something more hackable, so a Spherebot it is. One problem, though, was the lack of a controller board - the "official" site just uses a breadboard. That doesn't cut it with us, so we came up with our own design.

{% include gallery id="gallery" %}

<h2>Hardware</h2>
The design is very basic - an ATMega328P with a couple of Pololu stepper driver modules, a servo output, a crystal, and some connectors. Two stepper connectors, one for +12V and +5V in, and one FTDI-type serial connector.

{% include gallery id="gallery2" %}

Power is provided by an ATX power supply, and the serial to USB interface will be done with our [USB Wildcard board from earlier]({% post_url 2014-12-05-usb-wildcard-open-hardware-advent-calendar-day-5 %}). All of this is to keep this board as basic as possible.

Schematic and PCB design files can be <a href="https://github.com/SurrealityLabs/SpherebotController" target="_blank">found on our GitHub</a>.

<h2>Future plans</h2>
I'm currently working on building a Spherebot that will use this board.



I hope to finish that up over my Christmas break from work. I'll be posting more details on how we built it, along with a parts list and how to get the thing going, because that information seems to be a bit hard to find. This board might also feature prominently in a planned project for the DIYPinball project - a simple board for controlling two stepper motors is a useful thing to have lying around.

<h2>Conclusion</h2>
Not an exciting one today, but hopefully something that other people interested in making Spherebots will find useful.
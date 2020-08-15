---
id: 445
title: 'Black Magic Probe PCB: Open Hardware Advent Calendar Day 9'
date: 2014-12-09T23:47:09+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=445
permalink: /2014/12/black-magic-probe-pcb-open-hardware-advent-calendar-day-9/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
gallery:
  - url: /assets/images/projects/blackmagicprobe/photos/bmp-front.jpg
    image_path: /assets/images/projects/blackmagicprobe/thumbnails/bmp-front.jpg
    alt: "Black Magic Probe board, front"
    title: "Black Magic Probe board, front"
  - url: /assets/images/projects/blackmagicprobe/photos/bmp-top.jpg
    image_path: /assets/images/projects/blackmagicprobe/thumbnails/bmp-top.jpg
    alt: "Black Magic Probe board, top"
    title: "Black Magic Probe board, top"
gallery2:
  - url: /assets/images/projects/blackmagicprobe/schematic.png
    image_path: /assets/images/projects/blackmagicprobe/schematic-thumb.png
    alt: "Schematic"
    title: "Schematic"
---
Today's project is a rushed one, and part of our development effort for DIYPinball: our own PCB for the <a href="http://www.blacksphere.co.nz/main/blackmagic" target="_blank">Black Magic Probe</a>.

<h2>Overview</h2>
The Black Magic Probe is a debugging and programming tool for working with microcontrollers - more specifically, ARM Cortex-M series microcontrollers. It allows you to download code to the chips from your computer, and control the execution of that code, so you can develop and debug your projects more easily. We're looking at using it for the next series of DIYPinball boards as we try and move to a more Open Source-friendly development environment.

{% include gallery id="gallery" %}

The design is open source, and is available for sale, but the Black Magic Probe Minis that are currently sold don't seem have level shifting functionality - so they only work at 3.3V - and they only have one style of connector. Further, we needed a bunch, and shipping to Canada costs almost as much as the device itself. Since the design is open source, we decided to try doing our own design for the board, and make them ourselves.

<h2>Hardware</h2>
This is an advanced project - lots of tiny parts - so I'm not going to go into a ton of detail on this. The intended audience should be able to figure out the parts list and how to assemble it from the schematic and board layout. Also, I'm writing this on a deadline, and want to get this up on time, and that's really more of a factor at this point.

{% include gallery id="gallery2" %}

Basically, we've combined some of the <a href="https://github.com/blacksphere/blackmagic" target="_blank">alternative designs of the Black Magic Probe from their GitHub</a>, and added a connector for the LPCXpresso LPC-Link to the board, so we can use some of our existing boards with the probe.

The schematic, layout and CAM files can all be <a href="https://github.com/SurrealityLabs/BlackMagicProbePCB" target="_blank">downloaded from our GitHub</a>.

<h2>Future plans</h2>
We have tons of future plans for this project - mostly because it hasn't been tested yet. I've got a stack of 4 of them on my desk to be tested, and to be loaded with the USB bootloader, followed by the Black Magic Probe firmware itself. I intend to document the process for that when we get there (hopefully soon). I'll also write up the actual parts list, and we're hoping to put together a 3D printed case to protect the probe as well.

<h2>Conclusion</h2>
This one isn't actually done yet, but I needed to get something up before midnight, and I've been meaning to release this design anyways. So, loss-win-win, I guess.
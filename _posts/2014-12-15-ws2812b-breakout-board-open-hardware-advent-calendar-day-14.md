---
id: 460
title: 'WS2812B Breakout Board: Open Hardware Advent Calendar Day 14'
date: 2014-12-15T23:42:29+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=460
permalink: /2014/12/ws2812b-breakout-board-open-hardware-advent-calendar-day-14/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
gallery:
  - url: /assets/images/projects/ws2812-breakout/photos/fresh-boards.jpg
    image_path: /assets/images/projects/ws2812-breakout/thumbnails/fresh-boards.jpg
    alt: "Fresh WS2812 breakout PCBs"
    title: "Fresh WS2812 breakout PCBs"
  - url: /assets/images/projects/ws2812-breakout/photos/assembled-front.jpg
    image_path: /assets/images/projects/ws2812-breakout/thumbnails/assembled-front.jpg
    alt: "WS2812 breakouts, assembled (front side)"
    title: "WS2812 breakouts, assembled (front side)"
  - url: /assets/images/projects/ws2812-breakout/photos/assembled-back.jpg
    image_path: /assets/images/projects/ws2812-breakout/thumbnails/assembled-back.jpg
    alt: "WS2812 breakouts, assembled (back side)"
    title: "WS2812 breakouts, assembled (back side)"
  - url: /assets/images/projects/ws2812-breakout/photos/ws2812b-breadboard.jpg
    image_path: /assets/images/projects/ws2812-breakout/thumbnails/ws2812b-breadboard.jpg
    alt: "WS2812 breakouts, on a breadboard"
    title: "WS2812 breakouts, on a breadboard"
gallery2:
  - url: /assets/images/projects/ws2812-breakout/schematic.png
    image_path: /assets/images/projects/ws2812-breakout/schematic-thumb.png
    alt: "Schematic"
    title: "Schematic"
---
Apologies for the delay on this one. I knew that if I missed the schedule one day, it'd just cascade...

This one is another building block for future projects: a breakout board for the WS2812B LED, also known as the NeoPixel.

<h1>Overview</h1>
The WS2812B LED is more commonly known as the NeoPixel, a name popularized by Adafruit. It's an RGB LED with all the circuitry needed to control its brightness built right into the LED's package. All you have to do is provide power, connect the data in, and connect the next LED in the chain to the data out. Pretty simple, conceptually.

{% include gallery id="gallery" %}

There are a ton of other breakout boards for this LED available out there - Adafruit, Sparkfun, and a bunch of others all sell them. Ours is different because it copies the form factor of an old Sparkfun breakout for a different, similar module - their <a href="https://www.sparkfun.com/products/retired/10504" target="_blank">WS2801 breakout, to be precise.</a> This one was used on the Project Vending Machine 2.0, and has a lot of nice things going for it. It's fairly small while not being easy to lose, and has four mounting holes. Mounting holes are incredibly important when attaching stuff to other stuff.

<h1>Hardware</h1>
As indicated above, we blatantly ripped off SparkFun's design for the overall board. We changed the connectors, LED and control chip from 4-pin and an IC+LED combo to 3-pin and a WS2812B. The screw holes and text labels are all in the same place still.

{% include gallery id="gallery2" %}

The schematic itself is pretty simple - two connectors, a WS2812B, a bypass capacitor for the power supply, and two series resistors on the serial data lines. These are there primarily to absorb reflections on the serial line - basically, the long wires between modules can cause ringing that causes a large voltage to be present at either pin, which can damage or destroy the LED module. Having a resistor there absorbs that.

Schematic and PCB files are <a href="https://github.com/SurrealityLabs/WS2812Breakout" target="_blank">available at our GitHub</a>. Also included is our old WS2812 breakout - for the 6-pin version rather than the current 4-pin WS2812B - as well as the panelized versions. Those fit 4 boards into a space under 5x5cm, so you can get more boards for your buck.

If you want to order some of the boards from DirtyPCBs, <a href="http://dirtypcbs.com/view.php?share=2713&accesskey=6736006d60aca24d053561f56424ec3f" target="_blank">using this link gets us a kickback in the form of a discount</a>.

<h1>Future plans</h1>
This is going to factor into a bunch of future projects, because I love blinking LEDs. One of them is even part of the advent calendar (I hope).

<h1>Conclusion</h1>
A very useful building block for LED-related projects, even if it isn't a particularly exciting one on its own. Also, tested and known to work, which is a bonus.
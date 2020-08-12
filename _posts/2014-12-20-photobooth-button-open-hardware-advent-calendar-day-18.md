---
id: 471
title: 'Photobooth Button: Open Hardware Advent Calendar Day 18'
date: 2014-12-20T22:42:45+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=471
permalink: /2014/12/photobooth-button-open-hardware-advent-calendar-day-18/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
gallery:
  - url: /assets/images/projects/photobooth-button/photos/dome-bottom.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/dome-bottom.jpg
    alt: "Bottom of the button and dome"
    title: "Bottom of the button and dome"
  - url: /assets/images/projects/photobooth-button/photos/grab-button.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/grab-button.jpg
    alt: "Grab button assembly on the bottom"
    title: "Grab button assembly on the bottom"
  - url: /assets/images/projects/photobooth-button/photos/button-twist.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/button-twist.jpg
    alt: "Twist button assembly and pull to remove"
    title: "Twist button assembly and pull to remove"
  - url: /assets/images/projects/photobooth-button/photos/button-assembly.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/button-assembly.jpg
    alt: "Button assembly removed from dome"
    title: "Button assembly removed from dome"
  - url: /assets/images/projects/photobooth-button/photos/led-mount-removed.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/led-mount-removed.jpg
    alt: "LED mount removed from the button assembly"
    title: "LED mount removed from the button assembly"
  - url: /assets/images/projects/photobooth-button/photos/led-on-mount.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/led-on-mount.jpg
    alt: "With the LED mount removed, we see the two leads, wrapped around the bottom"
    title: "With the LED mount removed, we see the two leads, wrapped around the bottom"
  - url: /assets/images/projects/photobooth-button/photos/led-leads-unwrapped.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/led-leads-unwrapped.jpg
    alt: "Unwrapped the LED leads from the mount, to change the resistor"
    title: "Unwrapped the LED leads from the mount, to change the resistor"
  - url: /assets/images/projects/photobooth-button/photos/led-resistor-changed.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/led-resistor-changed.jpg
    alt: "Changed the resistor on the LED to allow 5V operation"
    title: "Changed the resistor on the LED to allow 5V operation"
  - url: /assets/images/projects/photobooth-button/photos/wires-soldered.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/wires-soldered.jpg
    alt: "Wires soldered to the button and LED"
    title: "Wires soldered to the button and LED"
  - url: /assets/images/projects/photobooth-button/photos/button-reassembled.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/button-reassembled.jpg
    alt: "Button reassembled after wiring"
    title: "Button reassembled after wiring"
  - url: /assets/images/projects/photobooth-button/photos/usb-wildcard-back.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/usb-wildcard-back.jpg
    alt: "USB Wildcard board wired for photobooth (back side)"
    title: "USB Wildcard board wired for photobooth (back side)"
  - url: /assets/images/projects/photobooth-button/photos/usb-wildcard-front.jpg
    image_path: /assets/images/projects/photobooth-button/thumbnails/usb-wildcard-front.jpg
    alt: "USB Wildcard board wired for photobooth (front side)"
    title: "USB Wildcard board wired for photobooth (front side)"

---
Still playing catch up, our next project is for those building a photobooth: a button to trigger it.

<h2>Overview</h2>
Photobooths are incredibly popular for weddings and other events these days, but are also incredibly expensive. Building one yourself is definitely an option, especially if you already have a decent camera and a computer you can dedicate to it. But wiring up a nice button takes some effort.

{% include gallery caption="Photos of the photobooth button." %}

What we've come up with here is just such a button, using the USB Wildcard board. It fades the LED in button on and off to attract attention, and when pressed, simulates hitting the spacebar to trigger photo taking.

<h2>Hardware</h2>
This is another one based on the [USB Wildcard]({% post_url 2014-12-05-usb-wildcard-open-hardware-advent-calendar-day-5 %}). It uses that along with a few other components to drive the LED and read the button.

I used a <a href="https://www.sparkfun.com/products/11274" target="_blank">SparkFun Big Dome Button</a>, which needs a modification to work properly. If you try to run the LED in the button on 5V, it will be dim - it's set up to use 12V, so the resistor is much too large for 5V operation. Refer to the photos above for how to disassemble it, but you basically remove the switch assembly by twisting it, and then pull out the LED assembly from the top of that. Unwind the leads from the plastic frame, and you can pull the LED and resistor out of the assembly. Replace the resistor with a 100 ohm unit, and reassemble.

The following is a very rough schematic of the button:

![Schematic of photobooth button]({{ site.url }}{{ site.baseurl }}/assets/images/projects/photobooth-button/rough-schematic.png)

So you've got PD0 of the USB Wildcard to a 1K resistor, and that to the base of a 2N3904 transistor. Emitter of that transistor to Ground, and Collector of it to the cathode side of the LED in the button. Anode of the LED to +5V, and then one side of the button to Ground. The other side of the button goes to PD3, and a 10K pull up resistor from PD3 to +5V.

<h2>Software</h2>
This requires the same Arduino setup as yesterday's project, [so follow the instructions there]({% post_url 2014-12-20-mousemover-open-hardware-advent-calendar-day-17 %}). Then, you can download the software from the <a href="https://github.com/SurrealityLabs/PhotoboothButton" target="_blank">GitHub project for this project</a>. Load the software and you should be good to go.

Here's a video of it in action:

{% include video id="A2p0BifjF50" provider="youtube" %}

For this video, I used <a href="http://sparkbooth.com/" target="_blank">Sparkbooth</a> but you can substitute whatever you like.

<h2>Future plans</h2>
About the only thing I'd like to add to the current version of this project is some debouncing for the button, but given the delays used to lock out the button after pressing it once, it's probably not a big issue. I'd also like to look at an even cheaper version using one of Microchip's new USB PICs - that one would require a cheap microcontroller and a couple resistors and capacitors.

<h2>Conclusion</h2>
This is an easy-to-build photo booth button that's still easy to customize, thanks to the use of the Arduino software to implement it. I hope someone finds it useful.
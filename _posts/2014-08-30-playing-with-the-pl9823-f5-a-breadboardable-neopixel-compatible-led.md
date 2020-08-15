---
id: 400
title: 'Playing with the PL9823-F5: a breadboardable Neopixel-compatible LED'
date: 2014-08-30T01:27:49+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=400
permalink: /2014/08/playing-with-the-pl9823-f5-a-breadboardable-neopixel-compatible-led/
categories:
  - Blog
gallery:
  - url: /assets/images/posts/pl9823-f5/photos/pl9823-f5-led.jpg
    image_path: /assets/images/posts/pl9823-f5/thumbnails/pl9823-f5-led.jpg
    alt: "PL9823-F5 LED"
    title: "PL9823-F5 LED"
gallery2:
  - url: /assets/images/posts/pl9823-f5/photos/pl9823-f5-pinout.jpg
    image_path: /assets/images/posts/pl9823-f5/thumbnails/pl9823-f5-pinout.jpg
    alt: "PL9823-F5 Pinout"
    title: "PL9823-F5 Pinout"

---
A fun new part has recently become available - the PL9823-F5. It looks like a standard 5mm RGB LED, with 4 pins and a diffused plastic forming the body of the LED itself.

{% include gallery id="gallery" %}

Inside, however, it packs a bit of a punch: a control chip that can set the brightness of Red, Green and Blue via serial data. It's similar to the popular WS2812 that Adafruit sells as the Neopixel - and it's fairly compatible with them to boot (the colour ordering is different). <a href="http://cpldcpu.wordpress.com/2014/06/16/timing-of-ws2812-clones-pd9823/">According to cpldcpu, the timing of these devices are compatible with the Neopixels</a>, so existing code (such as <a href="https://github.com/adafruit/Adafruit_NeoPixel">Adafruit's library</a>) will work.

There are a couple of important differences: first off, these are through hole, so they're easier for beginners and hobbyists to work with than the surface mount-only WS2812s. Also, Red and Green are swapped with respect to the Neopixel / WS2812. Other than that, they work identically.

<a href="http://www.led-genial.de/mediafiles//Sonstiges/PL9823.pdf">Here's a link to the PDF datasheet</a>, and <a href="http://www.aliexpress.com/store/product/PL9823-F5-5mm-round-hat-RGB-LED-with-PD9823-chipset-inside-full-color-frosted/312912_1707244750.html">here they are on AliExpress</a>. I just paid about $14 per hundred plus a little over $20 in shipping, which is a good deal. The pinout on the AliExpress page is wrong, by the way - use either the one in the datasheet or this fancy hand-drawn one I just made:

{% include gallery id="gallery2" %}

Here's a quick video of 5 of these LEDs in action, running Adafruit's strandtest sketch:

{% include video id="BMXJcchumYU" provider="youtube" %}

I'm formulating a few projects that could use these - I need to take a look at how little voltage they can get by on (they're rated to 4.5V on the datasheet), and how much current they draw. Odds are they're going to put out a lot of power supply noise much like the WS2812s, so I'll take a look at that, too.
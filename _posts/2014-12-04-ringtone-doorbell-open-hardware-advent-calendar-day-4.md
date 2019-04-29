---
id: 431
title: 'Ringtone Doorbell: Open Hardware Advent Calendar Day 4'
date: 2014-12-04T23:48:37+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=431
permalink: /2014/12/ringtone-doorbell-open-hardware-advent-calendar-day-4/
categories:
  - Open Hardware Advent Calendar
---
Today's project is something new. Really new. Working as of an hour ago, new. It's a customizable doorbell for kids to build.

<h1>Overview</h1>
The Ringtone Doorbell is a doorbell based on the Adafruit Trinket, meant for kids to build for their bedroom. They can customize the ringtone played by the bell using just about any <a href="http://en.wikipedia.org/wiki/Ring_Tone_Transfer_Language" target="_blank">RTTTL ringtone</a>. For anyone who didn't have a cell phone before about 2005, these long sequences of characters were how we used to add new ringtones on our phones. We'd sit there, keying them in on a numeric keypad, inevitably making a mistake so that it sounded completely wrong - but we'd eventually have the theme song from Beverly Hills Cop on our phones. (I'm old).

[AFG_gallery id='18']

The project consists of a button, a Trinket microcontroller from Adafruit, some batteries, and a speaker. When you push the button, the ringtone you program into it plays. You can put in whatever ringtone you want, as long as you have a computer running the Arduino software, and a USB cable.

This is actually an updated version of a project I designed for <a href="http://venture.mcmaster.ca/" target="_blank">McMaster University's Venture Science and Engineering camp</a> a number of years ago. Improvements in the tools available to us - like the Trinket - mean that this one is much easier for kids to customize and build.

<h1>Parts list</h1>
1 Half-size breadboard
1 Adafruit Trinket 5V
1 PCB-mount speaker
1 470 ohm resistor
1 10K ohm resistor
1 Button (I used a Pink arcade button)
1 3xAAA battery holder with switch (and batteries)
Some hookup wires
A computer running the Arduino software

<h1>Building the hardware</h1>
Since this is another breadboard-based project, I again went with Fritzing for the connection diagram. Note that the resistor going from the pin marked #0 on the Trinket is the 10K, and the one going from the pin marked #1 to the speaker is the 470 ohm. I used a piezo speaker on the Fritzing diagram, but a small 8 ohm (or higher) speaker, or a PCB-mount speaker, should work OK.

<a href="http://www.flickr.com/photos/61091961@N06/15763737909/" title="Ringtone Doorbell_bb" rel="lightbox"><img src="http://farm8.staticflickr.com/7569/15763737909_89433f21ec_n.jpg" width="303" height="320" alt="Ringtone Doorbell_bb" title="Ringtone Doorbell_bb" class="aligncenter"></a>

Frizting files and source code can be downloaded from <a href="https://github.com/SurrealityLabs/RingtoneDoorbell" target="_blank">our GitHub page for the project</a>.

You'll need to solder some wire to the button's pins - I twisted together a few feet of stranded 24 gauge wire. Stranded wire is better for something like this, since putting the button wherever it needs to go probably means it's going to have to bend. You'll want to tin the ends of the wire that plug into the breadboard with solder, to make sure they stay in the breadboard better.

<h1>Software setup</h1>
The Arduino sketch for this project requires that you install the <a href="http://playground.arduino.cc/Code/Bounce" target="_blank">Bounce library</a>. Adafruit has <a href="https://learn.adafruit.com/adafruit-all-about-arduino-libraries-install-use/how-to-install-a-library" target="_blank">good instructions on installing libraries</a>. The Bounce library is used for debouncing the button - a common problem with buttons is that they don't switch cleanly between on and off, and the bouncing around in between can cause software issues. We use special software to take care of this problem so that the bouncing doesn't mess up our program. You'll also need follow Adafruit's instructions for <a href="https://learn.adafruit.com/introducing-trinket/introduction" target="_blank">setting up the Arduino software to work with the Trinket</a>. 

The source code for the Arduino sketch can be downloaded from <a href="https://github.com/SurrealityLabs/RingtoneDoorbell" target="_blank">our GitHub page for the project</a>.

The software uses code borrowed from the <a href="https://github.com/ponty/arduino-rtttl-player" target="_blank">Arduino RTTTL library</a> coupled with some <a href="http://w8bh.net/avr/TrinketTone.pdf" target="_blank">tone generation code for the Trinket</a>. I may clean up this library at some point and make it available separately.

To customize the ringtone, you'll need to find another ringtone to use. Right now, it's loaded with the theme song from the movie Rocky. (I'm old). You can find other songs <a href="http://www.ringtonesgalore.co.uk" target="_blank">here</a>, and <a href="http://ez4mobile.com/nokiatone/rtttf.htm" target="_blank">here</a>, and <a href="http://mines.lumpylumpy.com/Electronics/Computers/Software/Cpp/MFC/RingTones.RTTTL" target="_blank">here</a>, and many other places with RTTTL ringtones. Googling should find you a bunch. Open the Arduino sketch, and find the place in the code that reads:

const char song_P[] PROGMEM =
"(a bunch of stuff)";

and put your ringtone in between the quotation marks.

Then, you should be set to load the code onto the Trinket. The <a href="https://learn.adafruit.com/introducing-trinket/setting-up-with-arduino-ide" target="_blank">Blink section on this page</a> goes over the steps required for that.

Once it's done loading, you should be able to press the button and have it play your ringtone! The red LED on the Trinket will blink along with the music.

https://www.youtube.com/watch?v=QJEbDc0YnsA

<h1>Future improvements</h1>
I don't have any future improvements planned for this project, but there's plenty that could be done to make it cooler. The USB interface on the Trinket could be used to send a message to your computer, showing you a message that someone's at the door if you have headphones on or something. You could also hook up a servo motor to it to wave a flag if someone's there. There are a lot of possibilities for enhancements.

<h1>Conclusion</h1>
I've seen kids have a lot of fun playing with this project in the past, so I hope it's one that more can enjoy in the future. It doesn't have a lot of parts, but does open a few doors for electronics and programming.
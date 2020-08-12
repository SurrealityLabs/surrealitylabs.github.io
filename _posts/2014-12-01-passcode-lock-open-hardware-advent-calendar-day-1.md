---
id: 417
title: 'Passcode Lock: Open Hardware Advent Calendar Day 1'
date: 2014-12-01T22:38:50+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=417
permalink: /2014/12/passcode-lock-open-hardware-advent-calendar-day-1/
categories:
  - Open Hardware Advent Calendar
tags:
  - ohwac2014
---
Our first project in the Open Hardware Advent Calendar is the Passcode Lock. This is a project I recently completed for the <a href='http://www.thenextsupergeek.com/' target='_blank'>Next Super Geek Challenge</a> at <a href='http://www.makerfairetoronto.com' target='_blank'>Maker Faire Toronto 2014</a>.

<h1>Overview</h1>
As part of the challenge, the participants had to find a code, and make sure they had the correct one at the challenge's booth. The system that the organizers had wasn't quite finished, so I offered to try and put something together with parts I had at home.

[AFG_gallery id='15']

The project has a keypad, an LCD screen, an Arduino, and some RGB LEDs (WS2812s / NeoPixels, to be more precise). The LCD shows a message asking the kids to enter their code with the keypad. When they're finished entering the code, if they're right, they see a message and some blue lights. If they're wrong, they see a different message, and some red lights.

https://www.youtube.com/watch?v=1igC-y8cXHs

<h1>Parts list</h1>
1 Arduino (I used a <a href="http://www.adafruit.com/products/91" target="_blank">USB Boarduino</a>, but just about <a href="http://www.adafruit.com/products/50" target="_blank">any Arduino</a> should work)
1 <a href="http://www.adafruit.com/products/198" target="_blank">20x4 Character LCD with parallel interface</a> (using the HD44780 or compatible controller - if it has 14 or 16 pins, it'll probably work)
1 100 ohm resistor
1 <a href="http://www.adafruit.com/products/356" target="_blank">10K ohm potentiometer</a> (this comes with the Adafruit LCD)
1 <a href="http://www.adafruit.com/products/419" target="_blank">4x3 or 4x4 keypad</a>
1 <a href="http://www.adafruit.com/products/239" target="_blank">Breadboard</a>
<a href="http://www.adafruit.com/products/153" target="_blank">A bunch of hookup wires</a> 
4 <a href="http://www.adafruit.com/products/1312" target="_blank">NeoPixels</a> (I used my own design, but the Adafruit ones will work just as well)

<h1>Building the hardware</h1>
This is a fairly simple project, so I'm just going to present a Fritzing project showing the breadboard setup. I've used a 16x2 LCD in the Frizting project, because that's all I found in the parts included. You should use a 20x4 LCD.

<a href="http://www.flickr.com/photos/61091961@N06/15741877837/" title="Passcode Lock Breadboard Diagram" rel="lightbox"><img src="http://farm8.staticflickr.com/7487/15741877837_ce01f837d8_n.jpg" width="265" height="320" alt="Passcode Lock Breadboard Diagram" title="Passcode Lock Breadboard Diagram" class="aligncenter"></a>

You can download <a href="https://github.com/SurrealityLabs/PasscodeLock/archive/master.zip" target="_blank">the Fritzing project and Arduino code here</a>, or <a href="https://github.com/SurrealityLabs/PasscodeLock" target="_blank">check it out on GitHub</a>.

The basic setup is this:
LCD pin 1 to ground
LCD pin 2 to +5V
LCD pin 3 to the middle pin on the potentiometer
LCD pin 4 (RS) to Arduino Digital Pin 2
LCD pin 5 (R/W) to Arduino Digital Pin 3
LCD pin 6 (E) to Arduino Digital Pin 4
LCD pin 7-10 not connected
LCD pin 11 (DB4) to Arduino Digital Pin 5
LCD pin 12 (DB5) to Arduino Digital Pin 6
LCD pin 13 (DB6) to Arduino Digital Pin 7
LCD pin 14 (DB7) to Arduino Digital Pin 8
LCD pin 15 to +5V
LCD pin 16 to the 100 ohm resistor
Other pin of 100 ohm resistor to ground

NeoPixel +5V to +5V (for all of them)
NeoPixel ground to ground (for all of them)
NeoPixel #1 DIN to Arduino Digital Pin 9
NeoPixel #2 DIN to NeoPixel #1 DOUT
NeoPixel #3 DIN to NeoPixel #2 DOUT
NeoPixel #4 DIN to NeoPixel #3 DOUT

Keypad Row 1 to Arduino Digital Pin 10
Keypad Row 2 to Arduino Digital Pin 11
Keypad Row 3 to Arduino Digital Pin 12
Keypad Row 4 to Arduino Digital Pin 13
Keypad Column 1 to Arduino Analog Pin 0
Keypad Column 2 to Arduino Analog Pin 1
Keypad Column 3 to Arduino Analog Pin 2
Keypad Column 4 (if you have it) to Arduino Analog Pin 4

<h1>Software Setup</h1>
The software makes use of the <a href="http://playground.arduino.cc/code/Keypad" target="_blank">Keypad library</a>, <a href="http://playground.arduino.cc/Code/Password" target="_blank">Password library</a>, and <a href="https://learn.adafruit.com/adafruit-neopixel-uberguide/arduino-library" target="_blank">Adafruit NeoPixel library</a>. You'll need to install them in your Arduino software - some instructions are <a href="https://learn.adafruit.com/adafruit-all-about-arduino-libraries-install-use/how-to-install-a-library" target="_blank">available here</a>. It also uses the LiquidCrystal library, which is included with the Arduino software. You should use a relatively recent version of the Arduino software - I was using 1.0.5r2. 

The software is based on some other examples I found online - specifically http://www.instructables.com/id/Password-Lock-with-Arduino/ and http://www.tech-zen.tv/episodes/shows/make-it-work/episodes/keypad-input-to-an-arduino-episode-11. I made some modifications to clean up the menus a bit, to use the keypad for the "enter code" button, and to add the NeoPixels.

One interesting thing about this project is that it uses the Arduino's Analog lines as Digital lines. Not many people know this, but they can be used for Digital I/O, so if you need more than 13 Digital I/O lines, just remember that Analog 0 is also Digital 14, Analog 1 is Digital 15, etc.

<a href="https://github.com/SurrealityLabs/PasscodeLock/archive/master.zip" target="_blank">You can download the code from here</a> along with the Fritzing project. You can check out the <a href="https://github.com/SurrealityLabs/PasscodeLock" target="_blank">GitHub project here</a>. After installing the libraries above, open the sketch in the Arduino software, customize the code, and download to your Arduino. You can change the code in the following line:

Password password = Password( "2008" );

Change the 2008 to whatever number you want - I'm not sure how long it can be, but 10 digits should be no problem.

<h1>Future improvements</h1>
I don't have any future improvements planned on this project at the moment, but there are definitely some places it could be taken. Most improvements would probably require freeing up some I/O lines, as we're kind of using all of them. Using an I2C LCD backpack like this Adafruit one would do the trick - note that Analog 4 and Analog 5, which are also the I2C port on the Arduino, have been left free for this reason. 

Once some I/O lines are freed up, it would be pretty easy to add more lighting, some sound effects, and maybe even a servo to control a locking mechanism. More NeoPixels can easily be added just by chaining them onto the ones already there - some software changes are all that's needed for those.

<h1>Conclusion</h1>
This is a pretty simple project - I put it together in a little over an hour by pulling together some spare parts and some pieces of other peoples' code. The parts that it's made of aren't too intricate, so it's fairly easy to assemble, but still a lot of fun.
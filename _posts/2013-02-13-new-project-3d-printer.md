---
id: 228
title: 'New Project: 3D Printer'
date: 2013-02-13T23:13:11+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=228
permalink: /2013/02/new-project-3d-printer/
categories:
  - Blog
  - Project Updates
tags:
  - 3dprinter
---
3D printers are the new must-have tool for people who make things. Personally, I want one for two reasons: designing and building custom enclosures for electronics projects, and putting the heads of my friends on Pez dispensers.

I've had the parts for months, and am hopefully going to get it working soonish. Here I want to go over the decisions (if any) behind each piece of the project.<!--more-->
<h1>What kind of printer?</h1>
The first decision to make when it comes to obtaining a 3D printer - well, after the decision to get one in the first place - is what kind. This, like virtually every stage, presents you with a bunch of sometimes-confusing options:
<ul>
	<li><a href="http://en.wikipedia.org/wiki/Fused_deposition_modeling" target="_blank">Fused-deposition modeling</a> (the kind that squirt plastic into layers, and then stack those to make things - like the <a href="http://www.makerbot.com" target="_blank">MakerBot</a> and <a href="http://reprap.org/wiki/Main_Page" target="_blank">RepRap</a>)</li>
	<li><a href="http://en.wikipedia.org/wiki/Stereolithography" target="_blank">Stereolithography</a> (the kind that use photosensitive chemicals like UV-curable resins)</li>
	<li><a href="http://en.wikipedia.org/wiki/Selective_laser_sintering" target="_blank">Selective Laser Sintering</a> (melting layers of fine powder with a laser)</li>
	<li><a href="http://candyfab.org" target="_blank">Selective Hot Air Sintering</a> (using hot air to melt confectioner's sugar)</li>
</ul>
Excluding the candy-based one purely for practicality reasons, FDM is the cheapest route right now. Making that decision only helps a bit, though, because now you get to make the following choices:
<ul>
	<li>Build or buy? You can build it yourself, or buy pre-made. Buying pre-made is usually pricier but less frustrating. Down the pre-built route lies options like the Makibox and MakerBot. Building it yourself gives you more flexibility in terms of size, materials you can use, etc. and is usually cheaper but more frustrating.</li>
	<li>Kit or source your own parts? A lot of places will sell you everything you need to build a 3D printer in one kit. This increases the price somewhat, but removes a lot of frustration. Buying parts on your own takes longer, but you again get flexibility and can save some money, especially if you already have some of the parts.</li>
	<li>What kind? I'd hazard a guess that most of the kits or self-built ones out there are some form of RepRap derivative. Not only is it a matter of deciding if you want a RepRap or not, it's a matter of what kind of RepRap. There are several. Within those there can be different versions / iterations, and each of those will have different build options.</li>
	<li>Let's assume that you've decided you're going to build a RepRap. Let's assume you've decided on a particular machine (say, Prusa Mendel Iteration 2). Now you get to make the following decisions:
<ul>
	<li>Heated build platform or no? You need heated to do ABS plastic, not necessary for PLA.</li>
	<li>Controller board. RAMPS, Sanguinololu, Printrboard, Generation 6, and many more options.</li>
	<li>Extruder / hot end. The extruder pushes the plastic filament, while the hot end melts it and squeezes it through a tiny hole. Options abound here - the most common extruder appears to be Wade's Geared Extruder, and as for hot end... wow. Hundreds of combinations, at least.</li>
</ul>
</li>
	<li>But wait! There's more! There's a standard set of RepRap printed parts - that is, the parts for your 3D printer that have to be built on another 3D printer - and then there are variations on those. Some offer a bunch of new features - like using linear bearings where plastic bushings were used before (MORE DECISIONS!) - and some are just easier to put together.</li>
</ul>
So what decisions have we made? Moving on to...
<h1>Our parts</h1>
At some point, I decided to make a <a href="http://reprap.org/wiki/Prusa_Mendel_(iteration_2)" target="_blank">RepRap Prusa Mendel Iteration 2</a>. I cannot for the life of me recall the exact reasons, but hackability and repairability factored into it. I went with a few non-standard choices for parts, so I've put together the manifest of parts below to talk about what it is we're building. I'd suggest visiting the link above there to get some idea of what I'm talking about in the bits below.
<h2>Printed parts</h2>
<a title="Z motor mounts" href="http://www.flickr.com/photos/61091961@N06/8469155947/" rel=""><img title="Z motor mounts" alt="Z motor mounts" src="http://farm9.staticflickr.com/8519/8469155947_69c4381e6d_t.jpg" width="100" height="75" /></a><a title="Various clamps" href="http://www.flickr.com/photos/61091961@N06/8467855169/" rel=""><img title="Various clamps" alt="Various clamps" src="http://farm9.staticflickr.com/8527/8467855169_cab03ef326_t.jpg" width="100" height="75" /></a><a title="Plastic pulleys" href="http://www.flickr.com/photos/61091961@N06/8467855311/" rel=""><img title="Plastic pulleys" alt="Plastic pulleys" src="http://farm9.staticflickr.com/8092/8467855311_dd1f726086_t.jpg" width="100" height="75" /></a><a title="Shaft couplers" href="http://www.flickr.com/photos/61091961@N06/8468949774/" rel=""><img title="Shaft couplers" alt="Shaft couplers" src="http://farm9.staticflickr.com/8227/8468949774_126721a5d6_t.jpg" width="100" height="75" /></a><a title="Bar clamps" href="http://www.flickr.com/photos/61091961@N06/8467855637/" rel=""><img title="Bar clamps" alt="Bar clamps" src="http://farm9.staticflickr.com/8368/8467855637_1c7268ac55_t.jpg" width="100" height="75" /></a><a title="Endstop brackets" href="http://www.flickr.com/photos/61091961@N06/8467855815/" rel=""><img title="Endstop brackets" alt="Endstop brackets" src="http://farm9.staticflickr.com/8376/8467855815_f9b4df150f_t.jpg" width="100" height="75" /></a><a title="Linear bearing blocks" href="http://www.flickr.com/photos/61091961@N06/8467855973/" rel=""><img title="Linear bearing blocks" alt="Linear bearing blocks" src="http://farm9.staticflickr.com/8226/8467855973_8c1090e201_t.jpg" width="100" height="75" /></a><a title="Y-axis motor mount" href="http://www.flickr.com/photos/61091961@N06/8468950334/" rel=""><img title="Y-axis motor mount" alt="Y-axis motor mount" src="http://farm9.staticflickr.com/8523/8468950334_b9bf6b1580_t.jpg" width="100" height="75" /></a><a title="Frame vertices" href="http://www.flickr.com/photos/61091961@N06/8467856173/" rel=""><img title="Frame vertices" alt="Frame vertices" src="http://farm9.staticflickr.com/8240/8467856173_74533fb856_t.jpg" width="100" height="75" /></a><a title="Idler X-End" href="http://www.flickr.com/photos/61091961@N06/8468950610/" rel=""><img title="Idler X-End" alt="Idler X-End" src="http://farm9.staticflickr.com/8099/8468950610_d2c826b3ca_t.jpg" width="100" height="75" /></a><a title="X carriage" href="http://www.flickr.com/photos/61091961@N06/8468950764/" rel=""><img title="X carriage" alt="X carriage" src="http://farm9.staticflickr.com/8373/8468950764_75bee6fd0c_t.jpg" width="100" height="75" /></a><a title="Motor X-End" href="http://www.flickr.com/photos/61091961@N06/8467856667/" rel=""><img title="Motor X-End" alt="Motor X-End" src="http://farm9.staticflickr.com/8086/8467856667_222f23b821_t.jpg" width="100" height="75" /></a>

The printed parts were sourced from a member of the <a href="http://site3.ca" target="_blank">Site3 coLaboratory</a> in Toronto at a <a href="http://www.toronto3dprinters.com" target="_blank">Toronto 3D Printers meeting</a>. Many are standard bits, though the ends of the X axis are an enhanced version with better retention of the linear bearings and better clamping of the smooth rods that the X carriage slides along. Also, the X carriage is a different design than normal, and the linear bearing holders for the build platform use screws to hold in the bearings rather than zipties.

These are just what he gave me - I didn't specify those particular versions - but they look like much better options, and I appreciate it. These parts set me back about $100.
<h2>Controller board</h2>
<a title="Sanguinololu control boards" href="http://www.flickr.com/photos/61091961@N06/8467854959/" rel=""><img title="Sanguinololu control boards" alt="Sanguinololu control boards" src="http://farm9.staticflickr.com/8100/8467854959_2541d5a4a8_t.jpg" width="100" height="75" /></a><a title="Heatsinks and thermal pads" href="http://www.flickr.com/photos/61091961@N06/8468948148/" rel=""><img title="Heatsinks and thermal pads" alt="Heatsinks and thermal pads" src="http://farm9.staticflickr.com/8091/8468948148_4d0c88fd3f_t.jpg" width="100" height="75" /></a>

Most people wind up going with the <a href="http://reprap.org/wiki/RAMPS_1.4" target="_blank">RAMPS</a> electronics package - an <a href="http://arduino.cc/en/Main/arduinoBoardMega2560" target="_blank">Arduino Mega</a> with the RAMPS board stacked on top of that, and the <a href="http://www.pololu.com/catalog/product/1182" target="_blank">Pololu A4988 stepper motor driver boards</a> stacked on top of that. The whole thing makes me sad. Some alternatives - such as the <a href="http://reprap.org/wiki/Printrboard" target="_blank">printrboard</a> or the <a href="http://reprap.org/wiki/Generation_6_Electronics" target="_blank">Generation 6 electronics</a> package - are much sleeker, but if you blow the stepper driver, you're in for some soldering work.

I decided that a nice middle ground was the <a href="http://reprap.org/wiki/Sanguinololu" target="_blank">Sanguinololu</a> board, with an ATMega1284P. Lots of RAM, lots of flash for code storage, easy to replace the stepper drivers, yet still compact and not a Frankensteinian agglutination of PCBs. You'll note I built two (except for the stepper drivers) - that's for the highly likely event that I fry one completely.

Boards were obtained on eBay, Pololu modules from <a href="http://www.a2aprinter.com" target="_blank">A2A Printer</a>, other parts were a combination of <a href="http://www.a2aprinter.com" target="_blank">Digi-Key</a> and my own stock.
<h2>Power Supply</h2>
<a title="Power Supply" href="http://www.flickr.com/photos/61091961@N06/8468947228/" rel=""><img title="Power Supply" alt="Power Supply" src="http://farm9.staticflickr.com/8528/8468947228_47903dbbcb_t.jpg" width="100" height="75" /></a>

The power supply used to power my PVR machine. When I added a UPS, this Power Factor Correcting PSU didn't cut it anymore - PFC PSUs have problems with "modified sine wave" (read: square wave) UPSs, it seems. So in went a non-PFC replacement, and this lovely Antec 500W unit went in the spares pile. Until now.

I may replace this with a dedicated 30A 12V PSU at some point in the future, but for now this'll work.
<h2>Motors</h2>
<a title="Steppers" href="http://www.flickr.com/photos/61091961@N06/8468949046/" rel=""><img title="Steppers" alt="Steppers" src="http://farm9.staticflickr.com/8390/8468949046_990d58fb10_t.jpg" width="100" height="75" /></a>

<a href="http://store.qu-bd.com/product.php?id_product=15" target="_blank">The steppers</a>, I obtained from <a href="http://www.qu-bd.com" target="_blank">QU-BD</a> when I ordered the heat bed and extruder (below). 5 kg*cm of torque, 3.6V per phase, 1.2A per phase. Most steppers seem to be lower voltage and higher current, which pushes the Pololu drivers very close to their 2A limit. Lower current = lower heat = longer life.
<h2>Extruder and hot end</h2>
<a title="QU-BD MBE Extruder" href="http://www.flickr.com/photos/61091961@N06/8467853463/" rel=""><img title="QU-BD MBE Extruder" alt="QU-BD MBE Extruder" src="http://farm9.staticflickr.com/8108/8467853463_a2180b95a2_t.jpg" width="100" height="75" /></a>

Looking at the assembly instructions for most hot ends and extruders gave me an ominous feeling of impending doom - so many ways to screw up. Further, most people seem to use power resistors rather than a proper heater in their hot ends, <a href="http://softsolder.com/2011/01/22/thing-o-matic-mk5-extruder-resistor-wrapup/" target="_blank">which they are most definitely not rated for</a>. Rather than mess around with this part, I opted to go with the <a href="http://www.qu-bd.com" target="_blank">QU-BD</a> <a href="http://store.qu-bd.com/product.php?id_product=11" target="_blank">MBE extruder</a>, pre-assembled with a cartridge heater. It came with insulation pre-attached - just wire it up and go. Looking forward to getting this working.
<h2>Heat bed</h2>
<a title="QU-BD Silicone Heater" href="http://www.flickr.com/photos/61091961@N06/8467853607/" rel=""><img title="QU-BD Silicone Heater" alt="QU-BD Silicone Heater" src="http://farm9.staticflickr.com/8249/8467853607_e1ffa6b092_t.jpg" width="100" height="75" /></a>

Most people use a PCB-based heat bed for doing ABS plastic. As with the power resistors as heaters, this is really not what FR-4 circuit boards were designed to do. I got the <a href="http://store.qu-bd.com/product.php?id_product=30" target="_blank">silicone heating pad</a> - something actually designed to heat things up - from <a href="http://www.qu-bd.com" target="_blank">QU-BD</a> as well, with integrated thermistor. I'm not planning on using it immediately, as I don't want to be doing ABS in my apartment without decent ventilation, but I have the option for later.
<h2>Various bits and bobs</h2>
<a title="Belt and pulleys" href="http://www.flickr.com/photos/61091961@N06/8467854599/" rel=""><img title="Belt and pulleys" alt="Belt and pulleys" src="http://farm9.staticflickr.com/8109/8467854599_6ab1ae4b0c_t.jpg" width="100" height="75" /></a><a title="Shaft couplers" href="http://www.flickr.com/photos/61091961@N06/8468948676/" rel=""><img title="Shaft couplers" alt="Shaft couplers" src="http://farm9.staticflickr.com/8240/8468948676_bb403c80ae_t.jpg" width="100" height="75" /></a><a title="Rods and hardware" href="http://www.flickr.com/photos/61091961@N06/8467854205/" rel=""><img title="Rods and hardware" alt="Rods and hardware" src="http://farm9.staticflickr.com/8524/8467854205_10f96f4770_t.jpg" width="100" height="75" /></a><a title="Linear bearings" href="http://www.flickr.com/photos/61091961@N06/8468948492/" rel=""><img title="Linear bearings" alt="Linear bearings" src="http://farm9.staticflickr.com/8249/8468948492_ccd7332586_t.jpg" width="100" height="75" /></a><a title="Laser-cut MDF build platform" href="http://www.flickr.com/photos/61091961@N06/8467853189/" rel=""><img title="Laser-cut MDF build platform" alt="Laser-cut MDF build platform" src="http://farm9.staticflickr.com/8527/8467853189_2b959faa97_t.jpg" width="100" height="75" /></a><a title="Spool of Plastic" href="http://www.flickr.com/photos/61091961@N06/8468947402/" rel=""><img title="Spool of Plastic" alt="Spool of Plastic" src="http://farm9.staticflickr.com/8094/8468947402_58fbcd3883_t.jpg" width="100" height="75" /></a>

&nbsp;

A standard Prusa Mendel kit uses T5 timing belts for X and Y axis drive, and printed plastic pulleys. The thought of the drivetrain of both these axes being based on plastic bits left me... ill at ease. I decided to get T2.5 belt and pulleys from Some Place On eBay. The pulleys are aluminum, rather than plastic, and the T2.5 stuff has tighter spacing on the teeth, which is supposed to mean smoother operation.

The metal shaft couplers are an eventual upgrade, and also from Some Place On eBay. For now, I'm sticking with the plastic ones, but again, plastic in the drivetrain freaks me out a bit.

The rods (threaded and smooth, pre-cut), washers, nuts, skate bearings, screws and such, I got in a kit from <a href="http://mixshop.com" target="_blank">Mixshop.com</a>. They have the distinct advantage of being a thirty minute walk from my apartment, and had a reasonable price on the kit. The laser cut MDF for the build platform was part of that kit, and I picked up a handful of linear bearings there as well. Also from there: my first spool of PLA plastic filament.
<h2>E-Stop switch</h2>
<a title="E-Stop switch" href="http://www.flickr.com/photos/61091961@N06/8471094874/" rel=""><img title="E-Stop switch" alt="E-Stop switch" src="http://farm9.staticflickr.com/8527/8471094874_fa13a2d020_t.jpg" width="100" height="75" /></a>

This switch I got from TMart. It's a twist-to-activate, push-to-deactivate switch, so it'll be perfect for an E-Stop in case of thermal or mechanical issue - hard to turn on, quick to turn off. I'm trying to figure out how to wire it in - I don't know that I want it handling all the 12V current for the system, so I'm thinking of wiring it to the signal on the ATX power supply to turn on.
<h1>Next steps</h1>
So that's the collection of Stuff I've assembled to build the printer. Assembly is scheduled to begin on Sunday. I'll hopefully be able to post some videos, photos, and other useful information from that process. I'll also link to some of the resources I'm using to put the thing together.
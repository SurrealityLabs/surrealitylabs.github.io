---
id: 368
title: 'New project: the PiMinder'
date: 2014-05-04T14:10:16+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=368
permalink: /2014/05/new-project-the-piminder/
categories:
  - Project Updates
tags:
  - PiMinder
---
We've started work on another new project, which we're calling the PiMinder. It's still a work in progress - don't have any photos yet - but it's coming along, so it's probably best to start writing about it before things get really, really hectic.

The PiMinder is a "market minder" - a device for keeping track of your shopping list. Old-fashioned ones were boards with common grocery items - milk, eggs, bread, etc. - painted on, and you'd check off what you need by putting a peg in a hole next to that item. The advantage of moving to a digital version is that you can synchronize it with a Web service, and check in on what you need from your smartphone, tablet or desk at work. That makes it a LOT easier for couples and families to keep track of what they need from the grocery store.

This wasn't our idea originally - <a href='http://www.instructables.com/id/Market-Minder/' target='_blank'>someone else already made one on Instructables</a>. There are a few problems with that one, though:
- No source code is given.
- The light-up buttons are REALLY expensive
- The app only works on iOS
- The WiFi module is pretty expensive

We're taking a different approach:

- Raspberri Pi Model A based - $25 for the board plus $5 for a WiFi adapter is about the same price as the WiFi module used in the Instructables one, and gives us the controller as well
- Circuit boards with six light-up buttons connected over I2C. We use the MCP23017 I/O expander rather than 74HC165 and 74HC594s gives us both inputs and outputs in one part, and lets us chain up to 8 boards of light-up buttons off the same I2C bus. The MCP23017 is well-supported on the Pi.
- An IKEA RIBBA picture frame as the enclosure. This can be scaled up depending on how many boards/items you need.
- Three sheets of laser-cut plastic added to the RIBBA frame. One to hold the circuit boards in the frame, one face plate, and one plate to mount labels on. These last two form the front panel of the device.
- A Node.js-based service for synchronizing grocery lists. This will use Angular.js for editing the list and using it from a desktop, tablet or phone. A Socket.io interface will allow real-time updates when a list is modified in any way. That way, the app and the device are always in sync.
- A much cheaper light-up button, similar to <a href='https://www.sparkfun.com/products/10443' target='_blank'>this guy from SparkFun</a>
- A Node.js-based program running on the Raspberry Pi to receive events from the web service and send updates based on buttons being pressed. Using Node.js makes it easy for us to use the same interfaces as the mobile app, which really simplifies the server. There are also some decent libraries for working with the MCP23017.


This architecture lets us make multiple PiMinders that point at the same list (but not necessarily the same items on that list), and have them all keep synchronized with each other. It also lets us keep costs down - estimated cost of the prototype is under $100, and subsequent ones are much cheaper due to minimum orders for circuit boards and what not.

This project is going to be evolving quickly. Currently, the boards are in and populated, and the server and web app are close to working. Laser cut plastics have been designed and just need to be actually cut. From there, it's a matter of assembling physically and finishing the Pi-side software. Getting the first version of that will be simple - getting a nice configuration interface going is going to be a bit trickier.

The plan is to have this ready to demonstrate in time for <a href='http://makerfairemontreal.ca/' target='_blank'>Maker Faire Montreal</a> on June 7 and 8. Even with spending a week in San Francisco for Maker Faire in... wow, less than two weeks... this is looking very doable.

One more thing: this project will be fully open-sourced when it's working. That includes the server-side Node.js code, the Raspberry Pi code, PCB layouts, and CAD files for the laser-cut plastic in the RIBBA frame.
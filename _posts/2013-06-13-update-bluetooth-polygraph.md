---
id: 299
title: 'Update: Bluetooth Polygraph'
date: 2013-06-13T09:58:53+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=299
permalink: /2013/06/update-bluetooth-polygraph/
categories:
  - Project Updates
tags:
  - BluetoothPolygraph
gallery:
- alt: Bluetooth Polygraph
  image_path: /assets/images/posts/bluetooth-polygraph/thumbnails/9029215135.jpg
  title: Bluetooth Polygraph. A quick shot of the Polygraph unit, with only the heart rate sensor and GSR sensors connected, and the lid taken off.
  url: /assets/images/posts/bluetooth-polygraph/photos/9029215135.jpg
- alt: Bluetooth Polygraph Sensors
  image_path: /assets/images/posts/bluetooth-polygraph/thumbnails/9029217155.jpg
  title: Bluetooth Polygraph Sensors. The finger GSR probes, and the Pulse Sensor Amped.
  url: /assets/images/posts/bluetooth-polygraph/photos/9029217155.jpg
- alt: Bluetooth Polygraph PCBs
  image_path: /assets/images/posts/bluetooth-polygraph/thumbnails/9019800349.jpg
  title: Bluetooth Polygraph PCBs. Front and back of the PCB for the Bluetooth Polygraph
  url: /assets/images/posts/bluetooth-polygraph/photos/9019800349.jpg
---
Just a quick update on the Bluetooth Polygraph project. More description is coming soon - possibly full documentation before the Waterloo Maker Faire this weekend - but this'll have to do for now.

The PCB has been assembled, and two of the three sensors tested:
{% include gallery id='gallery' %}

The pulse sensor (actually a <a href="http://pulsesensor.com/" target="_blank">Pulse Sensor Amped</a>) and the GSR sensor (based on / blatantly copied from Make's <a href="http://blog.makezine.com/projects/the-truth-meter-2/" target="_blank">Truth Meter</a>) both work nicely over Bluetooth. A processing app is currently graphing the data on a strip chart. I still have to build the respiration sensor, and get the app working on my Nexus 7, but I've already tried the stripchart (slavishly copied from <a href="http://www.openprocessing.org/sketch/6789" target="_blank">this code on OpenProcessing</a>) on the Nexus, and it worked nicely. Bluetooth functionality will be provided courtesy of <a href="https://github.com/arduino/BtSerial" target="_blank">the Processing BtSerial library from the Arduino folks</a>, which I'll be providing instructions on how to install, as well (since it doesn't come with a .jar file).

So there's still some work to do, but a manageable amount, and we should be done and possibly even documented in time for <a href="http://makerfairewaterloo.com/" target="_blank">Waterloo Maker Faire.</a>
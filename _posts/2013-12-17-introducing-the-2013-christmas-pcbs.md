---
id: 345
title: Introducing the 2013 Christmas PCBs
date: 2013-12-17T11:29:03+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=345
permalink: /2013/12/introducing-the-2013-christmas-pcbs/
categories:
  - Project Updates
tags:
  - ChristmasOrnament2013
---
Two years ago, I made a snowman circuit board. It was a fairly simple board - white with black silkscreen artwork, and a bunch of LEDs for the scarf and buttons on the snowman. A small PIC microcontroller handled blinking the LEDs in various patterns, and a button allowed the user to switch between patterns, as well as turn the unit off. Power came from a small watch battery. I made 100 of them, and they were a huge hit.

I've shown these at various Maker Faires over the two years since, and one question always came up: "Are you selling these?" Two years later, I've finally gotten the message, and came up with a new design. While the original was an all-Surface Mount affair (since I was the one building all of them), this new design is a through hole design, intended to be distributed as a soldering kit. There are four different designs, as well: a snowman, a snowflake, a candy cane, and a christmas tree. It's also designed around an AVR microcontroller so that an open source toolchain can be used.

In this post, I'll go over each of the boards quickly. Future posts will cover how the hardware and firmware works, how to assemble them, and how to modify the firmware to change the blinking patterns.

<h2>Candy cane board</h2>
<a href="http://www.flickr.com/photos/61091961@N06/11230475365/" title="IMG_6115.JPG" rel="lightbox"><img src="http://farm6.staticflickr.com/5477/11230475365_5f813a55d4_n.jpg" width="320" height="240" alt="IMG_6115.JPG" title="IMG_6115.JPG" class="aligncenter"></a>
The candycane board has 16 LEDs, alternating 8 red and 8 white in my construction. This can be changed when the user builds it on their own, of course. The board is made with a red solder mask and white silkscreen. It has seven patterns and an off state, which you can rotate through using the button on the right-hand side of the board. The patterns are:
<ul>
	<li>Off</li>
	<li>All lights on</li>
	<li>All lights blinking</li>
	<li>Alternating red and white</li>
	<li>Fill in from the short end of the candy cane</li>
	<li>Marquee</li>
	<li>Twinkling</li>
	<li>Fill in from the long end of the candy cane</li>

</ul>
Here's a video showing all of the patterns, in order:

<iframe width="560" height="315" src="//www.youtube.com/embed/yOKoYn_ZZcQ" frameborder="0" allowfullscreen></iframe>

<h2>Christmas tree board</h2>
<a href="http://www.flickr.com/photos/61091961@N06/11215550525/" title="IMG_6008.JPG" rel="lightbox"><img src="http://farm8.staticflickr.com/7307/11215550525_e65a27d5e5_n.jpg" width="320" height="240" alt="IMG_6008.JPG" title="IMG_6008.JPG" class="aligncenter"></a>
The Christmas Tree board has 17 LEDs, with a yellow star at the top and whatever arrangement the user wants for the lights in the tree. The board has standard green solder mask and white silkscreen. The patterns are:
<ul>
	<li>Off</li>
	<li>All lights on</li>
	<li>All lights blinking</li>
	<li>Marquee</li>
	<li>Fill in from the right</li>
	<li>Fill in from the bottom</li>
	<li>Twinkle all lights</li>
	<li>Twinkle all lights, except the star, which is always on</li>
</ul>
All of these are shown in the following video:

<iframe width="560" height="315" src="//www.youtube.com/embed/aqPifEERlBg" frameborder="0" allowfullscreen></iframe>

<h2>Snowman board</h2>
<a href="http://www.flickr.com/photos/61091961@N06/11231323315/" title="IMG_6163.JPG" rel="lightbox"><img src="http://farm8.staticflickr.com/7349/11231323315_fa7ef0a283_n.jpg" width="320" height="240" alt="IMG_6163.JPG" title="IMG_6163.JPG" class="aligncenter"></a>
The snowman consists of 10 LEDs: one red nose, three white buttons, and six LEDs along the scarf. The board has a white solder mask and black silkscreen. The patterns are:
<ul>
	<li>Off</li>
	<li>All lights on</li>
	<li>All lights blinking</li>
	<li>Nose on, all others marquee</li>
	<li>Nose and buttons on, scarf marquee</li>
	<li>Twinkle all lights</li>
	<li>Nose and buttons on, scarf twinkling</li>
	<li>Nose and buttons on, scarf fills in from the right</li>
</ul>
All of the patterns are shown in this video:

<iframe width="560" height="315" src="//www.youtube.com/embed/ES48Rtny06Y" frameborder="0" allowfullscreen></iframe>

<h2>Snowflake board</h2>
<a href="http://www.flickr.com/photos/61091961@N06/11229730296/" title="IMG_6059.JPG" rel="lightbox"><img src="http://farm4.staticflickr.com/3831/11229730296_bf38dab21d_n.jpg" width="320" height="240" alt="IMG_6059.JPG" title="IMG_6059.JPG" class="aligncenter"></a>
The snowflake is my favourite. It has 19 LEDs total, blue and white alternating along six spokes of a snowflake. It's on a board with blue solder mask and white silkscreen. It has the following patterns:
<ul>
	<li>Off</li>
	<li>All lights on</li>
	<li>All lights blinking</li>
	<li>Alternating blink</li>
	<li>Starburst (fill in from centre)</li>
	<li>Spiral fill</li>
	<li>Pinwheel (basically a rotating line)</li>
	<li>Twinkle</li>
</ul>

All of these are shown in this video:

<iframe width="560" height="315" src="//www.youtube.com/embed/GVwZ2Ub6quk" frameborder="0" allowfullscreen></iframe>

<h2>What's next</h2>
The boards have turned out very well. I'm still waiting on a few parts to arrive, so unfortunately I'm not going to be selling many this year. However, with a few tweaks I should have them ready well before Christmas next year.

The next few posts will go over the design and build instructions, as well as some lessons learned in the process. These boards are being released as open source, so you'll be able to make your own if you like and modify as you see fit.
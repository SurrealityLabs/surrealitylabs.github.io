---
id: 372
title: 'Ottawa Mini Maker Faire 2014: Badge Edition'
date: 2014-08-26T13:34:12+00:00
author: rglenn
guid: http://surrealitylabs.com/?p=372
permalink: /2014/08/ottawa-mini-maker-faire-2014-badge-edition/
categories:
  - Project Updates
  - Trip Reports
tags:
  - Badges
  - MiniMakerFaireOttawa2014
  - MMFO
---
The weekend before last in Ottawa (August 16-17, 2014) was the fourth annual Ottawa Mini Maker Faire. Mike, Chris and I exhibited the pinball machine - more on that in a trip report later. For this Faire, however, I worked with the organizers on making some special LED name badges for the Makers. This article serves as documentation of that project.

<h2>Timeline</h2>
Britta Evans-Fenton, one of the Faire’s organizers, came out to Mini Maker Faire Montreal (June 7-8, 2014 - again, trip report pending), so I got to talk to her there about this year’s Ottawa Faire. On the train trip back home to Toronto, I got the idea of having some sort of PCB name tag for the participants. I toyed with the concept for a while, and eventually came up with an idea, which I sent to Britta. This was June 18, at this point.

<a href="http://www.flickr.com/photos/61091961@N06/14789028018/" title="Maker Faire Badge Concept" rel="lightbox"><img src="http://farm4.staticflickr.com/3908/14789028018_e066931c8f_m.jpg" width="180" height="240" alt="Maker Faire Badge Concept" title="Maker Faire Badge Concept" class="aligncenter"></a>

We promptly both got busy, it seems - I dropped the project for a bit due to other priorities (such as Maker Faire Detroit preparations - once again, trip report pending). In the mean time, however, I somehow had the foresight to order sufficient dirt-cheap battery holders and power switches from Aliexpress. Power switches were something I wanted from the get go - we want the batteries to last all weekend in these things, and a good way to do that is to make sure that the light can be turned off at night, when you aren’t wearing it.

Around the first week of July, we started trading ideas back and forth, and I went back to the design. The idea at this point was for a silhouette for <a href='http://en.wikipedia.org/wiki/Centre_Block'>Centre Block</a> illuminated by some LEDs, the Mini Maker Faire Logo, some silkscreened text of the badge type (Staff, Volunteer, Maker, Sponsor), and a large silkscreened area for the wearer’s name.

On July 15, I did some 3D renders, and send off for prototypes, in two sizes - a mini one that would be best with a pin backing, and a larger one that would be best for a lanyard.

<a href="http://www.flickr.com/photos/61091961@N06/14952655186/" title="Small badge render" rel="lightbox"><img src="http://farm6.staticflickr.com/5556/14952655186_f49ec911d8_m.jpg" width="240" height="118" alt="Small badge render" title="Small badge render" class="aligncenter"></a><a href="http://www.flickr.com/photos/61091961@N06/14789027928/" title="Big badge render" rel="lightbox"><img src="http://farm6.staticflickr.com/5565/14789027928_9ef47a9fcf_m.jpg" width="240" height="118" alt="Big badge render" title="Big badge render" class="aligncenter"></a>

The boards came back on July 23rd - I went for express shipping - and while we were waiting for them to arrive, Britta and I came up with a slightly different plan, to cut down on costs:
- Use the lanyard-sized boards
- One kind of board - no silkscreen text for badge type. This meant we were ordering more of one kind of board, so the quantity discounts were higher, and we only paid one setup fee.
- Larger area for writing
- Different LEDs for the different badge types - colour-fade for sponsors, white for staff, blue for Makers
- Red PCBs for all

So when the boards did arrive, we already had a few changes ready to be done.

I quickly populated one when I got the boards, and fired a video up to Ottawa to demonstrate it.

{% include video id="Cj5B3VNK9mM" provider="youtube" %}

After looking at the prototype boards, I also decided that the lanyard holes needed to be bigger - about a quarter inch / 6.35mm. I made the changes and sent them off on July 29, once the Detroit Faire was done. They shipped out on August 4, and arrived on August 7. From the 8th to the 14th, I started assembly at home, first putting the battery holders and switches on each board, then starting to add LEDs as numbers came in for sponsors, Makers, etc. 

During this time I also did some battery life testing, 4 hours at a time. I was a bit worried about power draw given the lack of current-limiting resistors in the design. The Blue ones passed with flying colours - after 16 hours of on time, they were still usable. The colour fade ones did not - Blue went out after about 2 hours, and Green went out after about 6, leaving only Red working at the 16 hour mark. Because of this, the Partner badges with colour fade LEDs got 150 ohm resistors added by way of an x-acto knife and careful soldering.

Around the 14th, we remembered that we needed lanyards for these. I found some cotton and nylon cord at Wal-mart that fit the bill - 3’ sections worked perfectly for a lanyard (it came as 45’ lengths, hence the US Customary units). This was more expensive than I would have liked, but we were time-constrained. Wal-mart ran out of cotton cord, so I had to use Nylon as well, which required sealing to prevent fraying. This was done with fire, which had predictable results.

Apparently honey can be used to treat burns. I had no idea.

Badges were ready a few hours before we had to leave for Ottawa. Our departure was delayed a bit by car trouble, so Britta and I had to coordinate the transfer of badges. I had intended to deliver them the night before, but we got to our hotel at 3:30 AM, so that was out of the question, and us arriving at the Faire the moment it opened at 8:00 AM was… unlikely. So they were left with the front desk at the hotel.

From there, Britta and company handled distribution to each of the Makers, and there was much rejoicing and jubilation.

<h2>The Design</h2>
There were initially two designs: the small and the large. The small one was meant to be worn as a button, with a pin backing. It’s 1.95” by 1.45”, so it fits within Seeed Studios’s 5cm x 5cm maximum size. It doesn’t have a writing area on it, but does have two small (3.2mm) holes for a lanyard. The larger prototype was 3.4” by 1.95” and had a writing area, but was otherwise identical to the smaller one.

<a href="http://www.flickr.com/photos/61091961@N06/14789053089/" title="Front side of the small and large prototypes." rel="lightbox"><img src="http://farm4.staticflickr.com/3877/14789053089_c929306da1_m.jpg" width="240" height="180" alt="Front side of the small and large prototypes." title="Front side of the small and large prototypes." class="aligncenter"></a><a href="http://www.flickr.com/photos/61091961@N06/14789133988/" title="Back sides of the prototypes" rel="lightbox"><img src="http://farm6.staticflickr.com/5587/14789133988_d6d8122941_m.jpg" width="240" height="180" alt="Back sides of the prototypes" title="Back sides of the prototypes" class="aligncenter"></a>

Electrically, the badge is incredibly simple - a 3V battery holder (CR2032), a switch, and 3 LEDs in parallel. This is actually much too simple, really - the LEDs should each have a current limiting resistor. This decreases the brightness slightly, but decreases the initial current draw dramatically, depending on the forward voltage of the LEDs in use. It also ensures that the LEDs are of comparable brightness - otherwise one or two will be substantially dimmer than the other(s), because the characteristics of different LEDs can differ wildly. I made the decision, however, to omit these, for two reasons:
- I was planning on using LEDs with a forward voltage around 3V so the effects should be diminished, and
- It would save a TON of time if I didn’t have to solder in 600 resistors as well.

<a href="http://www.flickr.com/photos/61091961@N06/14789215847/" title="Badge Schematic" rel="lightbox"><img src="http://farm6.staticflickr.com/5595/14789215847_17c68e446d_m.jpg" width="240" height="114" alt="Badge Schematic" title="Badge Schematic" class="aligncenter"></a>

<h2>Construction</h2>
The badges were build first by soldering the battery holder to the back. This has nice big tabs and pads on the board, so it was easy, but to ensure that the battery holder stayed in place both during assembly and afterwards, I used some scrapbooking glue dots on an applicator to affix them to the boards. The specific one I used was an Ad Tech Dot Glue Runner, which is purple.
<a href="http://www.flickr.com/photos/61091961@N06/14975712135/" title="Adhesive" rel="lightbox"><img src="http://farm4.staticflickr.com/3842/14975712135_62486f4304_m.jpg" width="240" height="180" alt="Adhesive" title="Adhesive" class="aligncenter"></a><a href="http://www.flickr.com/photos/61091961@N06/14789040799/" title="Adhesive on the battery holder footprint" rel="lightbox"><img src="http://farm6.staticflickr.com/5582/14789040799_ce2c2242f3_m.jpg" width="240" height="180" alt="Adhesive on the battery holder footprint" title="Adhesive on the battery holder footprint" class="aligncenter"></a><a href="http://www.flickr.com/photos/61091961@N06/14972627261/" title="Soldered battery holder" rel="lightbox"><img src="http://farm4.staticflickr.com/3845/14972627261_22b4c85775_m.jpg" width="240" height="180" alt="Soldered battery holder" title="Soldered battery holder" class="aligncenter"></a>

Next, the tiny SMD switches get soldered on. You get good at these quickly when you do a couple hundred of them.
<a href="http://www.flickr.com/photos/61091961@N06/14952750266/" title="Power switch" rel="lightbox"><img src="http://farm6.staticflickr.com/5552/14952750266_3f85c7859b_m.jpg" width="240" height="180" alt="Power switch" title="Power switch" class="aligncenter"></a>

Once you’re done mounting those, the board joins the others in the pile on the floor.
<a href="http://www.flickr.com/photos/61091961@N06/14789123698/" title="Pile of badges" rel="lightbox"><img src="http://farm6.staticflickr.com/5592/14789123698_13dacdfd25_m.jpg" width="240" height="180" alt="Pile of badges" title="Pile of badges" class="aligncenter"></a>

Once the numbers for how many of which colour started coming in, the LEDs went on. For the Maker ones, we went with a 5mm Blue LED in the middle, angled down to have a spotlight effect on the Peace Tower, and also to avoid blinding the wearer as much as possible. The two side ones were lovely diffused 3mm Blue LEDs that I previously used on my Christmas ornaments. All of these LEDs came from my personal stores / junk bin.

Partner badges got diffused colour-fading LEDs that I had for another project, and Staff badges got white LEDs that I never actually tested, but we only needed 2 of these badges. All told, it took a couple of evenings to do the battery holders and switches, and then 3 more to do all the LEDs.

<h2>Artwork</h2>
Handling the artwork on the board is a bit tricky. I have a technique, though:
1. Prepare the art you need in your favourite drawing program (or whatever's available). I used Paint.NET in this case. I usually try and set the dimensions of the artwork based on rendering it to the PCB at 300 DPI - so if I want the final product to be 2 inches wide, I make it 600 pixels wide. Make sure the artwork is black and white.
2. Save it as a BMP file. Odds are you won’t be able to save it as a monochrome BMP - that's fine.
3. Open the BMP file in Microsoft Paint, and save it as a Monochrome BMP file.
4. Launch EAGLE, and create a library for your artwork.
5. Create a new package for the artwork.
6. Type “run import-bmp.ulp” in the command line in EAGLE and hit enter.
7. Open your BMP file, and select Black as the colour you want to import.
8. Set the scaling mode to DPI, and use whatever DPI value you used in step 1.
9. Set the starting layer to 25 (top silkscreen) to put the artwork on the top silkscreen, or 29 (tStop) to put it on the solder mask.
10. Hit Run.
11. Zoom in and delete the filename text in the lower left hand corner.
12. Save the library and add the package for the artwork to the board layout.

Note that this is mostly from memory - I reserve the right to come back and revise this to be accurate.

<h2>Design files</h2>
The design files - done in EAGLE CAD 5.12.0 - have been released on Github. Use them in good health.

<a href="https://github.com/SurrealityLabs/mmfobadges2014">https://github.com/SurrealityLabs/mmfobadges2014</a>

<h2>Results</h2>
The badges went over really well, and it was incredible seeing so many people using something I’d made in one place. If you look at different photos of the Faire and see a blue glow on someone’s face, odds are they were a Maker :)
- <a href="https://www.flickr.com/photos/126811168@N06/with/14951793736">Nuit Blanche's photos</a> - lots of blue glow there
- <a href="https://twitter.com/makerfaireott">Maker Faire Ottawa's Twitter stream</a> - even more blue faces
- <a href="http://ottawa.ctvnews.ca/video?clipId=418004">CTV Ottawa's coverage</a> - blue badges in motion! Also, the Pinball machine is there for like ten frames.

I got a lot of compliments about the badges, and some ideas from people for next year. I’d like to do something a bit more hackable - ideally something with a microcontroller - but I need to figure out what we can actually make it do, and still stay within a budget, both in terms of power and price. Having 200 people with a pair of AAAs hanging from their necks all day might not be so welcome, so staying with a CR2032 is ideal. Next time we're also definitely using pre-made lanyards - they're cheaper and less injury-prone for me.

In terms of changes, I would have liked to order things earlier so that we could have avoided paying for fast shipping (and then paying the shipping charge again in the form of HST and fees for charging HST). Also, I would have definitely added current-limiting resistors - towards the end of the first day I was seeing LED brightness differences which they would have prevented.
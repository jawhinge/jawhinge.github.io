---
layout: post
title: Beautiful Binary Disasters (1/2)
subtitle: Breaking images into submission (or useless data)
tags: [visuals, glitch]
comments: false
---

In typical western white suburban fashion, let me take you back to when I was about 16 and all the pretty girls around me were getting into camera filters. I'd often see pictures with weird chunks of them in different colors or pictures in anaglyph 3D. Did that inspire me? Fuck no, not in any way you'd like to know about.

**What actually happened** was, about that time I got into Linux. From Linux I learned that you could recover lost files from corrupted HDDs or USB sticks. Having been on the receiving end for a few such fateful data fuck-ups, I decided to give it a whirl. At this time, an old and decrepid USB stick found its way to my 4-th hand [HP Compaq 6715B](https://www.cnet.com/products/hp-compaq-6715b-15-4-turion-64-x2-tl-64-vista-business-2-gb-ram-120-gb-hdd-series/) and off I go typing in the esoteric incantations that would necromance it back to life. The result were... *rather iffy*. 

They looked broken - streaks of magenta-green corruption covered whatever I had managed to salvage. But there was something mesmerizing about *the sound structure, filled with something broken*. 

I couldn't tell you when I decided to start breaking files on purpose if you pointed a gun to my head but I still have the result. 

![Beach Glitch](https://i.imgur.com/VAIBEe3.jpg){: .mx-auto.d-block :}
*This being a picture of a beach I took with my brand spanking new Motorola MotoG*

How did I get it to look like that with zero image editing software? 

## Editing images as audio 

It's really simple. Get yourself [Audacity](https://www.audacityteam.org/) or an editor that can handle raw binary data. The closest you'll get an image to digestible raw binary data is a bitmap. That is to say, you will need to convert your nudes to **.bmp** before you art them up. This tipically produces large files in the ballpark of 50ish MBs so buckle up. Using Audacity as an example, you will have to go about it like so: 


#### Importing

- Pick an image with good contrast. Defined, sharp edges will make all the difference. Colors don't matter much because you'll end fucking them up later. 
- Convert that image to .BMP
- In Audacity do **File>Import>Raw Data**
- Navigate to your image and double click to open
- It is **VERY IMPORTANT** to choose **A-Law** or **U-Law** as Encoding. Remeber this because you **MUST** export with the same encoding
- For byte order, the default settings will work but you can try little endian or big endian

![Settings](https://i.imgur.com/BcjThcA.png)

Now we're at a very tricky part of the whole ordeal. The thing is, part of this audio is the file's *header* - the piece of info that signifies what file this is, where it starts and stops and generally tells your computer how to read it. It is usually located in the first **<30** seconds of the audio representation. Sometimes it's easy to see as there is a different waveform where the header is that looks nothing like the rest of the file. **DO NOT** apply effects to that part of the audio because you'll corrupt the file and make it useless. 

![Waveform](https://i.imgur.com/cC5D8tH.png)
*This is how your audio may look. I have no idea why this image has no data on one channel and a lot on the other but that's the magic of it*

Play your newly imported image-audio and bask in the glory of your first harsh noise track. Just don't blow out your speakers.


#### Pick an effect - try delays, compressors, reverbs, anything

I notice that subtle changes in parameters or subtle effects in general produce better results. If you go too hard you get a completely garbled mess of pixels that (to me at least) does not look coherent enough to be beautiful. 


![Tunnel Glitch](https://i.imgur.com/jOGOHzM.jpg)
*This is a picture of an underpass that has been processed with heavy compression and reverb*

![Subtle Tunnel Glitch](https://i.imgur.com/tJ5ahu3.jpg)
*This is the same underpass with more subtle compression and no reverb. See how it takes on an almost film grain-like look? Preatty neat-o*

{: .box-note}
**A word of advice:** Sometimes you'll fuck up your file by doing nothing wrong. Save on every version and name your versions correctly. For example, I use "underpass-comp-reverb-heavy.bmp". Save often and Undo / Ctrl + Z is your friend. 


#### Exporting

It will be way easier if you enable visible file extensions on whatever system you use. On windows, you can do that from the View menu on the File Explorer toolbar. If you're on Linux you don't need me to tell you how to do that. If you're on macOS, go fuck yourself. 

- To export, start with **File>Export>Export Audio**
- From the following menu, navigate to where you want to save your file
- Pay attention to **Save as type** - choose **Other uncompressed files**
- For **Header**, choose **RAW (header-less)**
- For **Encoding** choose whatever you picked when opening the file - **A-Law** or **U-Law**

![Export](https://i.imgur.com/dCVL7DI.png)

If you didn't bodge the whole thing, you should have a jumbled mess of pixels that vaguely represents what was on your initial photo. 
So go ahead - have fun. Throw a dick pic in there, garble it up beyond recognition or maybe go for subtlety and structure - **the world's your oyster <3**.  

PS: Find a bunch of examples on my second instagram - <a href="https://www.instagram.com/resolve_reject/" target="_blank">@resolve_reject</a>



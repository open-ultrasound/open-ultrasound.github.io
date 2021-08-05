---
layout: post
title:  "Phantom Results"
subtitle: "Images of an ATS539 Phantom with the Open Image System"
date: 2021-02-09
image: '/assets/2021-02-09-ultrasound-phantom/phantomAsmall.png'
author: Jed
---

Ultrasound phantoms are as close to the "gold standard" for evaluating imaging system performance as there is.  Our collaborators at the [UIUC Bioacoustics Research Lab](https://www.brl.uiuc.edu/) sent us one of their ATS539 phantoms.  Here's a photograph of our test setup.

<a href="\assets\2021-02-09-ultrasound-phantom/phantomSetup.png">
<img src="\assets\2021-02-09-ultrasound-phantom/phantomSetup.png" style="width:400px;"/>
</a>

There were a number of challenges with this setup. Most are related to those discussed in our ["Challenges and Oppurtunities"](https://www.open-image.org/2021/02/10/challenges.html) blog post. 

In particular, the 16-channel limitation required us to scan the ultrasound probe along the surface of the phantom (or else we'd only image a narrow, difficult to interpret "slice"). We placed the phantom on a linear translation stage in an attempt to move it relative to the probe in controlled steps. However (as anyone who has ever tried this will likely tell you), there is considerable stiction between the probe and the transducer. Swapping the coupling agent (water, mineral oil, and ultrasound gel) did not help. This caused the probe to "stutter" during scanning, resulting in uneven motion between subsequent 16-channel "images." One consequence of this is that we can sometimes see multiple images of the same target in the full reconstructed image:

<img src="\assets\2021-02-09-ultrasound-phantom/phantomAmisalign.png" style="width:400px;"/>

Another particularly troublesome challenge was the system's very low data rate. This, coupled with our narrow imaging window, made it essentially impossible to adjust imaging parameters (e.g., gains, TGC curves) in real time. As such, considerable room for optmization of image quality was likely left on the table. 

Nevertheless, we obtained images of three sections of the phantom. The first was primarily of the anechoic targets:

<img src="\assets\2021-02-09-ultrasound-phantom/PhantomA.png" style="width:400px;"/>

While not (yet) the quality one would expect from a commercial system, the key features of the phantom are present. Given our struggles overcoming the system's limitations, we were very pleased with this image. 

The second image is of the grayscale targets. The lack of real time feedback was particularly troublesome for this target group - we almost certainly used suboptimal gain settings for this run. 

<img src="\assets\2021-02-09-ultrasound-phantom/phantomB.png" style="width:400px;"/>

Our third image is of the phantom's "resolution array>" Here the biggest challenge was the probe stuttering as the phantom moved below it. There are some promissing indications that our system performs well (particularly between 1 and 2 centimeters along the horiztonal axis) but there are two many double-images to make any firm conculsions. 

<img src="\assets\2021-02-09-ultrasound-phantom/phantomC.png" style="width:400px;"/>


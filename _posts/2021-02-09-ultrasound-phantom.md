---
layout: post
title:  "Phantom Results"
subtitle: "Images of an ATS539 Phantom with the Open Image System"
date: 2021-02-09
image: '/assets/2021-02-09-ultrasound-phantom/phantomAsmall.png'
author: Jed
---

Ultrasound phantoms are as close to the "gold standard" for evaluating imaging system performance as there is.  Our collaborators at the [UIUC Bioacoustics Research Lab](https://www.brl.uiuc.edu/) sent us one of their ATS539 phantoms.  Here's a photograph of our test setup.

<img src="\assets\2021-02-09-ultrasound-phantom/phantomSetup.png" style="width:400px;"/>

There were a number of challenges with this setup. Most are related to those discussed in our "Challenges and Oppurtunities" blog post. 

In particular, the 16-channel limitation required us to scan the ultrasound probe along the surface of the phantom (or else we'd only image a narrow, difficult to interpret "slice"). We placed the phantom on a linear translation stage in an attempt to move it relative to the probe in controlled steps. However (as anyone who has ever tried this will likely tell you), there is considerable stiction between the probe and the transducer. Swapping the coupling agent (water, mineral oil, and ultrasound gel) did not help. This caused the probe to "stutter" during scanning, resulting in uneven motion between subsequent 16-channel "images." One consequence of this is that we can sometimes see multiple images of the same target in the full reconstructed image:

<img src="\assets\2021-02-09-ultrasound-phantom/phantomAmisalign.png" style="width:400px;"/>

Another particularly troublesome challenge was the system's very low data rate. This, coupled with our narrow imaging window, made it essentially impossible to adjust imaging parameters (e.g., gains, TGC curves) in real time. As such, considerable room for optmization of image quality was likely left on the table. 

Nevertheless, we obtained images of three sections of the phantom. The first was primarily of the anechoic targets:

<img src="\assets\2021-02-09-ultrasound-phantom/phantomA.png" style="width:400px;"/>

While not (yet) the quality one would expect from a commercial system, the key features of the phantom are present. Given our struggles overcoming the system's limitations, we were very pleased with this image. 

The second 


Our prototype system is limited to 16 channels (while our imaging probe has 128 elements). 


Below are some sample results covering a wide range of pulse center frequencies, durations, and shapes. We have very good command over the excitation and the output waveform below the transducer's center frequency (5-6 MHz). Above that, the impulse response of the transducer begins to dominate. This is not unexpected.

<img src="\assets\2020-10-02-customized-waveforms/4 MHz; 1 Pulse(s).png" style="width:400px;"/>

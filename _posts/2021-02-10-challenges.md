---
layout: post
title:  "Challenges and Oppurtunities"
subtitle: "On Honest Discussion of the Open Image System's (Current) Limitations"
date: 2021-02-10
image: '/assets/2021-02-10-challenges/doubleImage.png'
author: Jed
---

As hinted at in our last blog post, there are a number of limitations with our first generation Open Image system. Given that we built an ultrasound machine from the ground up, this is not surprising. Here's our honest assessment of the current state of the system:

- It works! Let's not forget this. It transmits high-voltage excitation pulses then conditions and digitizes the low-level analog echoes. The raw data can be beamformed and beamformed lines can be stacked to form human-readable images. 
- It only has 16 channels. In order to image most anything worth imaging the probe must be scanned([with its own challenges](https://www.open-image.org/2021/02/09/ultrasound-phantom.html)). In hindsight, we should have considered adding multiplexing between the pulser ICs and the probe connector - we could have then made use of all 128 probe channels to form a relevant image from a single probe placement). The limited number of channels also limits the degree of beamforming and beamfocusing possible. 
- The data transfer rate is slow. Too slow. With our focus on the ultrasound circuits and logic, not enough time was spent optimizing the data transfer from the FPGA development board to the host PC. It currently takes on the order of a few seconds to transfer 16 lines of prebeamformed data. With beamforming (and/or averaging) the time to collect a single (16 channel) "image" quickly scales to minutes. This makes real-time adjustment of imaging parameters (e.g., gains, TGC curves) - common practice with commercial systems - next to impossible. While we are happy that the system collects data, we need to spend more effort on getting the data off the Open Image system and onto the host PC quickly - a speedup of many orders of mangitude is needed. 
- The receive channel timing is not consistent for subsequent shots. The current FPGA logic has a bug where the time between pulser T/R switch switching to Rx mode and the ADC start is not consistent from "shot" to "shot." Luckily, the switching creates a small step change in the DC level of the recieved signal that can be used, in post-processing, to align the signals. 

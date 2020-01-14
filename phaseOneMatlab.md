This document specifies a Matlab interface to the Phase I Open Image controller. It is intended that most firmware functionality can be derived from this specification.

Frame: enough data to generate a single image
Shot: one transmit/receive cycle; there may be many (perhaps 100's) of shots per frame
Channel: corresponds to one element on the ultrasound transducer

Note: it is still TBD how to handle multiple frames. Will discuss. Perhaps we limit ourselves to one frame in Phase I.

```matlab
%% Transmit Side:
% Global Settings:
frame(Nframe).shot(Nshot).tx.fs %"sample" rate (TBD how to specify)
% Per Channel Settings
frame(Nframe).shot(Nshot).channel(Nchannel).tx.enable %is channel enabled

frame(Nframe).shot(Nshot).channel(Nchannel).tx.levelSequence %2 = Vpp0, 1 = Vpp1, 0 = RTZ, -1 = Vnn1, -2 = Vnn1; e.g., [2 -2] would be  single-cycle square wave (Note we want to be able to do transmit-side beamforming; what timing resolution do we have on one pulse's firing relative to the others?)

% What resolution do we have over the timing between channel firings?

% What control, if any, do we have over the T/R switch settings?

%% Receive Side:
% Global Settings:
frame(Nframe).shot(Nshot).rx.fs %sample rate

frame(Nframe).shot(Nshot).rx.N %number of samples to acquire

frame(Nframe).shot(Nshot).rx.tgc %time gain compensation input (TBD how to specify)(Note this will drive a DAC that drives the AFE)

frame(Nframe).shot(Nshot).rx.aaf %anti-aliasing filter setting (TBD how to specify)

%% Per Channel Settings (TBD if we can actually control all of these on a per-channel basis)

frame(Nframe).shot(Nshot).channel(Nchannel).rx.enable %is channel enabled

frame(Nframe).shot(Nshot).channel(Nchannel).rx.lna %LNA Gain

frame(Nframe).shot(Nshot).channel(Nchannel).rx.pga %PGA Gain (if applicable)

%% Data collection: (Still TBD pending how we decide to handle multiple frames)

oi = openimage;

oi.open; %open connection with device

for ii=1:1:NFrame

  thisFrame = frame(ii);
  
  oi.queue_frame(thisFrame); %sends frame structure (defined above) to device
  
  res = oi.get_frame(thisFrame); %requests frame data from device (res includes a Nshot x Nchannel x Nsample matrix of raw data)
  
end

oi.close; %closes connection with device
```
Want to comment on, edit, or view the history of this document? Visit it on [GitHub](https://github.com/open-ultrasound/open-ultrasound.github.io/edit/master/phaseOneMatlab.md).

---
created: 2025-10-14T12:35
modified: 2025-10-14T13:06
---
Some people have asked me about various things on my stream, so I'm documenting them here to share.

## Ad Breaks
I typically do 3 minutes of continuous ads per hour. This allows for 2 things on Twitch:
1. Incoming viewers don't get any pre-roll ads, so they can start watching immediately.
2. During the 3 minute ad break, everyone (including me) can get up and take a little break from the computer screen. No one misses anything. The general exception to this is during collabs with friends.

There are 2 parts to setting this up -- setting the automatic ad manager and announcing it in chat.
### How to set 3 minutes of ads every hour
- Go to Twitch > Creator Dashboard > Monetization > Ads
- Turn on Ad Manager if it's not activated (this runs ads automatically according to a schedule)
- Ad Minutes Per Hour: 3 (this turns off pre-roll ads for new viewers for the entire hour)
- Ad Length and Frequency: Manual, as long as possible
- In Advanced Settings,
    - First Ad Delay: 1 minute (as short as possible so you can start the ads ASAP)
    - I turn off auto snooze because it throws me off but it's up to you
    - I also turn on ad-free viewing for subscribers
- Back to General in the first page, disable Pre-roll ads
- You can enable Stream Display Ads if you want, they're like banners under the video and less intrusive, but I've never seen them so I don't know if they actually exist

### How to announce an ad break in chat
I also have my bot announce ad breaks as a reminder to both chat and myself that there's an ad break coming soon. Depending on the bot you use, you may or may not have this available to you. These are the ones that I used or have looked into for others.

> [!info]- [Streamer.bot](https://streamer.bot/)
> - Ads soon: the Trigger is `Twitch > Ads > Upcoming Ad`. Mine is set for 1 minute before
> - Ads running: the Trigger is `Twitch > Ads > Ad Run`. I announce that ads are starting, delay for 182000ms (about 3 minutes 2 seconds for latency), then announce again that ads have ended

> [!info]- StreamElements
> Go to Stream Elements > Chatbot > Modules > Chat Alerts and enable Adbreak. You can change the message in the settings attached to it.

## Captions
Captions are a very good thing to have, especially if you have viewers who don't have access to audio. There are 2 types of captions, closed and open.

**Closed captions** are not visible / "closed" to the viewer until they enable it. This is what a lot of people refer to as "CC". I use the [Closed Captioning OBS Plugin](https://github.com/ratwithacompiler/OBS-captions-plugin) for this; it works as a standalone OBS plugin and is also available in the VODs.

**Open captions** are embedded into the video (so the viewer can't turn it off), but you can do some fun things with it, like change the styling and create a dedicated box for it. You can use [curses](github.com/mmpneo/curses/) to create Speech to Text (STT) captions to display on OBS and Discord.

## Text to Speech (TTS)
Some days my environment is really noisy, or I'm simply nonverbal, and it doesn't make sense for me to use my mic. On those days, I use the TTS section of Curses to read out my typing. 

You can select where the audio output is sent. In my case, I want it to go to other applications, like OBS for stream or Discord for VC. I use [VB-CABLE Virtual Audio Device](https://vb-audio.com/Cable/index.htm) to do this.
- For OBS, I add a new Audio Input Capture and set it to `CABLE input`. To hear the TTS readout myself, I also go to Advanced Audio Properties and set the Audio Monitoring for CABLE input to `Monitor and Output`
- For Discord, I set the output of Curses to `CABLE input`, then I set the input in Voice & Video to `CABLE output`. Now other people in the VC can hear the TTS readout

Unfortunately, Curses is not really maintained anymore (the last update was 2 years ago), so you may have to look into some other application.
+++
author = 'ogreload3d'
date = '2026-09-27T10:47:20+09:00'
draft = false
title = '20260927_104715 Hugo Posting Rules'
tags = ['hackerman']
title-images = []
ending-images = []
table-of-contents = true
toc-auto-numbering = true
+++

## It's been a good weekend for hacking

Overall in this weekend I have been doing the most basic bitch version of hacking: reading manuals and setting up stuff. Like Hugo, I love Hugo. It just works. I haven't had the time to set up any cool CSS yet but hey, once I do, it'll work retroactively for ALL the posts!

## Goodbye, Retropi! Hello, Pihole!

I had this Raspberry Pi with retropi set up, but recently I haven't had much time to play video games through it. Usually when we'd go on a vacation, then we would play Panel de Pon on the SNES. Now we can do the same thing through the Switch, so my Retropi kinda started gathering dust.

Reddit has been introducing me to the homelab subreddit, where nerds set up their computers to do... pretty much whatever, it's kinda hard to describe WHAT they're doing, since I literally don't know. Everybody's just posting their home servers there. Anyway, there was a thread about what got you into homelabbing and 90% of the answers were just "pihole". 

[Apparently a pihole is just a raspberry pi that will block ads for you. Quite nifty huh!](https://docs.pi-hole.net/)

Man I can't believe how many ADS I am seeing per day. Like I'm sure it has happened to you as well: you just wanna get a recipe for dinner, and instead the recipe site will start with a life story about their dog or whatever, then open up 4 different VIDEO ADS and start autoplaying them. God help you if you forgot to turn on the wifi, since your mobile data will be obliterated. Did you even get to the recipe before that? NOPE!

Well, with the Pihole, this problem will be gone, as long as you set it up all nicely.

The way it works is that you tell the router to get DNS info from the raspberry pi, and raspberry pi (the pihole) will then do it all.

The setup process is actually VERY easy:

https://www.reddit.com/r/pihole/comments/18bz80p/comment/kc7jy74

```
Things you need: Pi with an ethernet port (recommended), Memory card, card reader, ethernet cable, and Pi power supply (you can also use old phone chargers as long as the voltage/wattage is fine).

Or if you keep your PC on all the time then You can go the docker path. Idk how different it is. Here's how I setup mine on a Pi4B:

Install Pi Imager from official website

Install RPi OS Lite on the memory card, set a username and password during installation alongside other settings like wifi, keyboard layout etc.

Insert card in Pi and connect it to your router and check what IP was assigned to. Also set that IP as static so that it never changes.

SSH using that IP by opening cmd.exe (Windows machine) and typing "username@ip" (replace username with the one you set and IP with the one your router assigned it.

run "sudo apt update && sudo apt upgrade -y" command once you login to your Pi. This will update and apply all the settings.

Install Pi-hole using the command on their website.

Keep pressing yes/continue. If you're asked to select DNS upstream, select Cloudflare (recommended) but you're free to use Google or anything else. In the end you will be greeted with installation complete and a password for yout Pi-Hole interface. Change it if you want to by running "sudo pihole -a -p" command

Login to your router and go to something similar to DHCP settings (It is different for different routers, never used Sagemcom).

Assign "Primary DNS" as your Pi-Hole's IP.

Reconnect all the devices.

This is just a TL;DR version that should get you up and running. Things like keeping piOS and pihole updated, the blocklists updated, adding more, using other features are covered in the docs.
```

Unbelievably, once I had it all set up, I would no longer see any ads on the recipe sites. Amazing!

I really don't feel it's made my browsing that much faster, but I've only had it up for about an hour. Already I have blocked about 800 queries, with 23% block rate. Hmm. I'll think about making it more strict and set up all the automation later. 


## Hugo beats Wordpress every single day

It's like so easy to just type in the 
```bash
hugopost my-cool-new-post
``` 

and bam I got it all going! I can literally do all the crap I wanna do as long as I have the time and willing to put in the effort lol.

I used to have a bunch of blogs, I'm sure my old blogspot is still up somewhere, but idk, it kinda hits different when you got your markdown files and you can just push them straight into github and it'll do all the posting for you automatically. Right now my Github Actions will publish straight to neocities and the github pages.

I don't know man, at work I let AI do all the coding for me, but these days I'm reconnecting to computing by making things more physically tangiable. The Pihole was one thing, but this blog is also more "mine" than my code at work will ever be.

I don't even care if this crap will look good on the CV or not - like who cares! As long as I'm getting paid, it's all good.

## How to have fun with your computer

- idk just go for it man. [I've been playing Transport Tycoon Deluxe (well, OpenTTD)](https://www.openttd.org/downloads/openttd-releases/latest) and it sure scratched some itches I didn't even know I had.
- I finally played that [Theme Hospital game](https://en.wikipedia.org/wiki/Theme_Hospital) I really wanted as a kid. It's p cool but idk, I'm not getting how to play it "properly". All my doctors end up having melties and quit their jobs. Maybe it's a part of the simulation haha
- set up servers, connect to them through ssh or whatever lol
- set up blogs and screw around github actions.
- just bee yourself. :bee: (oh man this would be dope af if I could figure out how to get emoticons working on my blog dude, somebody write it down for me LOL)
---
layout: post
title: "Bye bye Experia Box (V10)"
date:   2022-11-09 19:30:00 +0200
author: Sakis Kasampalis
tags:
- router
- fiber
- internet
- dd-wrt
---
![WAN settings](/assets/experia.jpeg)


This is something that I wanted to do for years, and it finally happened. I got rid of the Experia Box.

You know the story. You switched to a fiber Internet connection. Is there anything better? I love it!

And then comes your "generous" <abbr title="Internet Service Provider">ISP</abbr>. They gave you the Experia Box, in my case V10 (ZTE H369A). A crappy device with poor WiFi connectivity and insecure protocols, limited configuration options, and no firmware upgrade possibilities.

The easiest way to fix most of these issues is to buy a decent router that supports installing custom firmware (in my case dd-wrt) and connect it to the Experia Box. The Experia Box then still acts as the Internet gateway, but you can disable all other options (e.g. WiFi) and use your router's better features instead.

So first step, find a good router that supports custom firmware. I bought a Netgear R6700 v3 and replaced the stock firmware with dd-wrt (not covered here, there is enough good material of how to do that out there). Connecting the new router to the Experia Box worked like a charm, and fixed the WiFi connectivity and security issues.

But I don’t want to stop there. I have that extra ugly box that acts as my <abbr title="Wide Area Network">WAN</abbr> gateway. I really, really, want to replace it with my router. Is that even possible? Checked online, and there was a lot of confusion. People claiming that this is not possible, because you need the modem capabilities of the Experia Box, and a router doesn't support this. But such statement doesn’t make sense. I’m using fiber, not <abbr title="Digital Subscriber Line">DSL</abbr> or the cable network, so why do I need a modem? To be sure, I called my ISP, and they confirmed that it should be possible to replace the Experia Box with my own router.

And now comes the tricky part. After a lot of reading (and cursing) due to the infamous WAN <abbr title="Internet Protocol">IP</abbr> 0.0.0.0 (basically, no Internet) issue, I’m happy to share with you the working settings. Disclaimer: The following settings are working for me because I only use Internet, no IP TV (who needs that when there’s Netflix and online TV channels) or a landline. People claim that it’s still possible to use those with the proper router and cofigurations, but I don’t need them, so that's not my problem :)

Step 1: <abbr title="Point-to-Point Protocol over Ethernet">PPoE</abbr>. You will find the credentials in the Experia's config settings. Your ISP can also help you with this.

![PPoE settings](/assets/ppoe.png) 

Step 2: <abbr title="Virtual Local Area Network">VLAN</abbr>. My ISP says that Internet goes over VLAN 6, which must be tagged and have priority 1.

![VLAN settings](/assets/vlan.png)

Step 3: Configure the WAN port to use VLAN 6 (under Setup/Networking).

![WAN settings](/assets/wan.png)

Step 4: Reboot the router.

You should now get a WAN IP. Looks simple when you see it complete, but it was very painful and frustrating to achieve this. So goodbye Experia Box, I hope that I won’t need you ever again.



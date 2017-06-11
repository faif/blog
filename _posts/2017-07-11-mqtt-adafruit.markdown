---
layout: post
title: 'Sending MQTT data to Adafruit IO using a Pycom board'
date:   2017-06-11 19:20:00 +0200
author: Sakis Kasampalis
tags:
- iot
- adafruit
- micropython
- pycom
---

In this tutorial I'll show you how to send MQTT data to [Adafruit IO][adafruit]. The hardware that I'm using is a [LoPy] (only its WiFi interface) and an analog temperature sensor [TMP36]. The circuit is rather simple:

![Electronic circuit](/assets/tmp36.png)

 The capacitor between the A/D pin and the ground is used to eliminate noise, but you can skip that if you don't care. For the same reason (increasing the measurement accuracy) I'm averaging 100 sample A/D measurements. Measuring only once works too, but it's less accurate.
 
 Enough with the theory, let's move on to the code. I'll reuse most of Pycom's [MQTT tutorial code][tutorial]. The main difference is that I'll connect to Adafruit IO instead of HiveMQ. So if you don't have an Adafruit account yet, now is a good time to create one. Here's the code:

<script src="https://gist.github.com/faif/6da69d341a29c2b29c450343d2c20ddf.js"></script>

Note that I'm sending the temperature value every 30 seconds which is an overkill. In practice you should use a more pragmatic interval. By default Adafruit IO feed creates a private feed showing the measurements and a nice graph. I've changed it to public so that you can [take a look too][feed].

Happy Hacking :)

[adafruit]: https://io.adafruit.com
[LoPy]: https://www.pycom.io/product/lopy/
[TMP36]: https://www.adafruit.com/product/165
[tutorial]: https://docs.pycom.io/pycom_esp32/pycom_esp32/tutorial/includes/mqtt.html
[feed]: https://io.adafruit.com/ierax/feeds/office-temperature

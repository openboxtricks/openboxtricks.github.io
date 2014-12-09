---
layout:     post
title:      screensaver and screen lock
date:       2014-12-04
summary:    set your machine up to save power
categories: openbox power
---

__Openbox has no screensaver installed. With modern setups the biggest 
requirement is to power down the monitor or screen.__

This can be done simply with `xset dpms 600 600 600` (for a 10 
minute timeout) in the openbox startup script .

I dont need this setting.  I am either at my machine or I lock the 
screen.  When I lock the screen I want the screen to turn off.  I 
achieve this with this script

{% highlight bash %}
#!/bin/bash
xset dpms 8 8 8
amixer -q sset Master mute
slock
xset dpms 0 0 0
{% endhighlight %}    

This sets the monitor to power down after 8 seconds (enough to allow 
password entry), mutes the sound and locks with slock from suckless 
tools.  slock is an uber minimal screenlock

I also have a hotkey assigned to simply turn the screen off using 
this script:

{% highlight bash %}
#!/bin/bash
sleep .4
xset dpms force off
{% endhighlight %} 

---
layout:     post
title:      volume osd
date:       2014-12-04
summary:    display the volume with an osd
categories: openbox script
---

__This script can be used to increase, decrease or mute the alsa mixer 
and display the volume and mute status with an on screen display.__

Install `aosd_cat` and then copy this script. Bind it 
to the mousewheel of the desktop or any keys you like.

{% highlight bash %}
#!/bin/bash
#================================================================================
### mixer-osd
#================================================================================

case $1 in

   volup) A="$(amixer sset Master 1.5dB+ | grep "Left:" \
      | awk '{print $6}' | sed 's/0dB/dB/' | tr -d '[]')" ;;

   voldown) A="$(amixer sset Master 3dB- | grep "Left:" \
      | awk '{print $6}' | sed 's/0dB/dB/' | tr -d '[]')" ;;

   mute)
      case $(amixer set Master toggle | grep "Left:" \
         | awk '{print $7}' | tr -d '[]') in
            on) A="$(amixer sget Master | grep "Left:" \
      | awk '{print $6}' | sed 's/0dB/dB/' | tr -d '[]')" ;;
            off) A="mute" ;;
      esac ;;

   *) echo "Usage: $0 { volup | voldown | mute }" ;;

esac

MUTESTATUS=$(amixer get Master | grep "Left:" | awk '{print $7}' | tr -d '[]')

if [ $MUTESTATUS == "off" ]; then
   OSDCOLOR=red; else
   OSDCOLOR=green
fi

killall aosd_cat &> /dev/null

echo "$A" | aosd_cat -p 8 -y -55 -x -7 \
-n "Ubuntu bold 22" -u 2000 -o 2000 -R $OSDCOLOR -f 0

{% endhighlight %}    

You may need to examine amixers output for your card and modify the 
awk, sed and tr commands.

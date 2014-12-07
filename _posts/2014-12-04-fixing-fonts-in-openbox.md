---
layout:     post
title:      smooth fonts in openbox
date:       2014-12-04
summary:    How to make fonts look great in openbox
categories: openbox fonts
---

The font settings in lxappearance never worked for me.  Here is how I solved this issue:

put the following in `~/.Xresources`

{% highlight bash %}
Xft.dpi: 100
Xft.antialias: true
Xft.hinting: true
Xft.rgba: rgb
Xft.autohint: false
Xft.hintstyle: hintslight
Xft.lcdfilter: lcddefault
{% endhighlight %}    

http://lovingthepenguin.blogspot.co.uk/2011/07/fixing-ugly-qt-fonts-in-openbox-fluxbox.html

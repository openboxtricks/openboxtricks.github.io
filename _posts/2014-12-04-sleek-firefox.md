---
layout:     post
title:      sleek firefox
date:       2014-12-04
summary:    Making firefox look better
categories: openbox firefox
---

__Firefox doesn't hide the titlebar when maximised.
Also I use it halfscreen and the titlebar is surplus to requirements.__

Here, openbox's undecorate feature somes to our rescue.

![firefox!](/images/screenshot--091214--16-25-21.png)

Remove it by placing the following in `~/.config/openbox/rc.xml` in 
the `<applications>` section

{% highlight xml %}
<application name="Navigator">
    <decor>no</decor>
</application>
{% endhighlight %}    

You can use the empty area of the tabbar or the alt key to move the 
window.
Close with the menu or a keyboard shortcut.
How often do you close your browser anyway?

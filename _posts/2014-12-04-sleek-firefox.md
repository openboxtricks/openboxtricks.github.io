---
layout:     post
title:      sleek firefox
date:       2014-12-04
summary:    Making firefox look better
categories: openbox firefox
---

Firefox doesn't hide the titlebar when maximised.  Also I use it 
halfscreen and the titlebar is surplus to requirements.

![firefox!](/posts/screenshot--091214--16-25-21)

Remove it by placing the following in `~/.config/openbox/rc.xml` in 
the `<applications>` section

{% highlight xml %}
<application name="Navigator">
    <decor>no</decor>
</application>
{% endhighlight %}    

You can use the empty area of the tabbar to move the window.  Close 
with the menu or a keyboard shortcut.  How often do you close your 
browser anyway?

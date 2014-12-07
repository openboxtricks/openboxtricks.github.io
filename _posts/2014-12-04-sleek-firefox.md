---
layout:     post
title:      sleek firefox
date:       2014-12-04
summary:    Making firefox look better
categories: openbox firefox
---

Firefox doesn't hide the titlebar when maximised.  Also I use it 
halfscreen and the titlebar is surplus to requirements.  Remove it 
with:

put the following in `~/.config/openbox/rc.xml` in the `<applications>` section

{% highlight xml %}
<application name="Navigator">
    <decor>no</decor>
</application>
{% endhighlight %}    

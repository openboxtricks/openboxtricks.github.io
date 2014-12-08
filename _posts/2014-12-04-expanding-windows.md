---
layout:     post
title:      magic expanding windows
date:       2014-12-04
summary:    Have your windows fill an available space
categories: openbox windows
---

You can place a window in an empty area of desktop and have it 
expand to fill the space.  This lets you quickly arrange a few windows.

Set up a keybind

{% highlight xml %}
<keybind key="W-G">
  <action name="Unmaximize"/>
  <action name="ToggleDecorations"/>
  <action name="MoveResizeTo">
	<width>0</width>
	<height>0</height>
  </action>
  <action name="MoveRelative">
	<x>5</x>
	<y>5</y>
  </action>
  <action name="MoveToEdge">
	<direction>north</direction>
  </action>
  <action name="MoveToEdge">
	<direction>west</direction>
  </action>
  <action name="GrowToEdge">
	<direction>south</direction>
  </action>
  <action name="GrowToEdge">
	<direction>east</direction>
  </action>
</keybind>
{% endhighlight %}    

This can also be made to be triggered by doubleclicking on the 
taskbar or one of the window controls, for example the rollup icon

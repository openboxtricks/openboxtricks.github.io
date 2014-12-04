---
layout:     post
title:      Disabling the power button
date:       2014-12-04
summary:    Instant off is no fun at all
categories: jekyll pixyll
---

Without a session manager the default setting for the power button is to
instantly shutdown your computer.  This is particularly problematic on a
laptop where the power key may be close to the keyboard.  To disable the
power button follow these instructions:

Check your `/etc/systemd/logind.conf` file.

It should look like this:

{% highlight ruby %}
[Login]
#NAutoVTs=6
#ReserveVT=6
#KillUserProcesses=no
#KillOnlyUsers=
#KillExcludeUsers=root
#Controllers=
#ResetControllers=cpu
#InhibitDelayMaxSec=5
#HandlePowerKey=poweroff
#HandleSuspendKey=suspend
#HandleHibernateKey=hibernate
#HandleLidSwitch=suspend
#PowerKeyIgnoreInhibited=no
#SuspendKeyIgnoreInhibited=no
#HibernateKeyIgnoreInhibited=no
#LidSwitchIgnoreInhibited=yes
#IdleAction=ignore
#IdleActionSec=30min
{% endhighlight %}

Uncomment the line that says `#HandlePowerKey=poweroff` 
and change the value to `ignore`

    HandlePowerKey=ignore

Then restart the logind with the command

    sudo restart systemd-logind

or reboot your computer.

[source](http://askubuntu.com/questions/362914/how-to-prevent-the-power-button-to-shutdown-directly-the-system)


# ios-ntp

An application testbed and a network time protocol client for iOS. This is a
work in progress.

Created by Gavin Eadie on Oct17/10
Copyright 2010 Ramsay Consulting. All rights reserved.

### About

The clock on an iPhone, iTouch or iPad is not closely synchronized to the
correct time. In the case of a device with access to the telephone system, there
is a setting to enable synchronizing to the phone company time, but that time
has been known to be over a minute different from UTC.

In addition, users may change their device time and severely affect applications
that rely on correct times to enforce functionality.

This project contains code to provide time obtained from standard time servers
using the network time protocol (NTP: RFCs 4330 and 5905). The implementation is
not a rigorous as described in those RFCs since the goal was to improve time
accuracy to with in a second, not to fractions of milliseconds.

### This Fork

This is a fork from the original source at
[http://code.google.com/p/ios-ntp/](http://code.google.com/p/ios-ntp/) that
provides ios-ntp as a *static* iOS framework. This makes its use easier and
avoids symbol clashing.

Why fork? Well, because git and github are much more convenient than google code
for me. I (jbenet) am subscribed to the RSS feed of the original project and
will merge any upstream changes.

### License

[Artistic License/GPL](http://dev.perl.org/licenses/)

This is the work of Gavin Eadie

### Usage

To add to your project, download [ios-ntp.tar.gz](https://raw.github.com/jbenet/ios-ntp/master/release/ios-ntp.tar.gz),
and add `ios-ntp.framework` to your project. Then, simply call:

    [NSDate networkDate];

As soon as you call it, the NTP process will begin. If you wish to start it at
boot time, so that the time is well synchronized by the time you actually want
to use it, just call it in your AppDelegate's didFinishLaunching function.

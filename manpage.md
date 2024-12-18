# xwatchwin 1 "28 Dec 1995" "Georgia Tech"

## NAME

xwatchwin - watch a window on another X server
## SYNOPSIS

```
xwatchwin [\-v] [\-u UpdateTime \
DisplayName { \-w WindowID | WindowName }
```

## DESCRIPTION

 xwatchwin  allows you to peek at a window on another X server.

To use it, you must specify the display name of the machine you want to watch, then the name of the window on that machine.

 Xwatchwin will attempt to connect with the X server hostname:0.0, and if successful, will try to retrieve a copy of
the window in which you specified interest.

You may specify the window you want to watch either by name or by its
window id, usually a hexidecimal number.  Usually specifying the
window by name is simpler, although not all windows have names
associated with them; in that case you must use the window id option.

If the window you want to watch is not in a viewable state,
 xwatchwin will tell you so and exit.  If while you are watching
a window it becomes 'unviewable',  xwatchwin will wait until the
window becomes 'viewable' again.

 xwatchwin was written as an aid to a class for people learning
to use X.  The idea is that the instructor would type into an xterm
window on his/her display and the students would use  xwatchwin 
to see what the instructor typed.  The students could then type the
same thing in their own terminal windows.  Hopefully others will find
equally (if not more) constructive uses.

## OPTIONS
-u  updatetime

This option specifies how often (in seconds) you want to get a new
copy of the window you're watching.  It is in effect a 'sample rate'. 
By default,  xwatchwin updates your copy of the window as often
as it can.  The time it takes to actually do the update is dependent
on the speed of the X server on both machines, the speed of the
intervening network, and other factors.

-w  windowID 

This option specifies the window you want to watch by number, for
example, "0x50000b".  Use the xlswins(1) command to get a list of
window id's and possibly their names on the remote server. 

You must specify a window to watch either by name or by id. 
Specifying a window to watch by name is usually easier if you know
what you're looking for.

## EXAMPLES

If there is an X server on the remote machine "crow" and if on that
server there is a window called "X Terminal Emulator", you can watch
that window by typing

```xwatchwin crow X Terminal Emulator```

If there is a window on "crow" that has no name but has a window id of
"0x50000b", you can watch it by typing

```xwatchwin crow -w 0x50000b```

If you want to get new copies of a window only every 30 seconds, you
can do so by typing

```xwatchwin crow -u 30 -w 0x50000b```

## "SEE ALSO"

xlswins(1), xwininfo(1), xdpyinfo(1),

## BUGS

 xwatchwin doesn't support the \-display option.  You must set
the display on which the  xwatchwin window is created by changing
your DISPLAY environment variable.

If the window you're watching is resized while  xwatchwin is
getting a new copy of that window, the program will crash.  The
smaller your update interval, the more likely you are to experience
this bug (although it hasn't happened all that often to me).

 xwatchwin can now deal with two displays of different depths. 
There is special-case code for the conversions between 1-bit displays
and 8-bit displays (either direction) which may garble the image on
some machines.  The general case code should work on anything, albeit
somewhat more slowly.  

One note: ABSOLUTELY no attempt is made to make
the colors match up.  If you're on a 5-bit display, and you're
monitoring someone elses 8-bit display, the conversion just takes his
8 bits and chops the top 3 bits off, and puts it on the screen.  Maybe
in the next version...

## COPYRIGHTS

Copyright 1992 \- 1995, Q. Alex Zhao

Copyright 1989, George D. Drapeau
.SH AUTHORS

Light-weight version by Q. Alex Zhao  azhao@cc.gatech.edu .

Display depth conversion code added by John Bradley  bradley@cis.upenn.edu .

Original version by George D. Drapeau, Stanford University,
Academic Information Resources / Systems Development,
 drapeau@jessica.stanford.edu .

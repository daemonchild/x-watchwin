## Version 1.1.1 README

```
XWatchwin V1.1.1  -----------------------------------------------------------
28 Nov 1995, by Q. Alex Zhao <azhao@cc.gatech.edu>

A quick bug-fix release.

XWatchwin V1.1    -----------------------------------------------------------
22 Nov 1995 "Happy Thanksgiving", by Q. Alex Zhao <azhao@cc.gatech.edu>

A bug-fix release.

XWatchwin V1.0    -----------------------------------------------------------
25 Dec 1993 "Merry Christmas", by Q. Alex Zhao <azhao@cc.gatech.edu>

This code was posted on comp.sources.x quite some time ago.  I've been
playing with it and I have made some changes (adding features,
removing bugs).  The program does one thing: watch over someone else's
window (probably on another display).

To build (use an ANIS C compiler):
	xmkmf
	make

Most of the time its use is instructional, but someone may try to use
it to spy on other people.  Make your X Window System secure!


Original "README" -----------------------------------------------------------

I've taken the 'xwatchwin' code that was posted on comp.sources.x a
few days ago, and added two new features to it.  The major feature is
you can now run the program and have it work out even when the two
displays (yours, and the one you're monitoring) are of different
depths.  It should work for any combinations of depths, and it has
special case code for displaying a 1-bit window on an 8-bit display,
and displaying an 8-bit window on a 1-bit display.  It does this
reasonably quickly, however, I can't guarantee that the special case
code'll work on every server.  I've tried it out on all combinations
of 8-bit RTs, 8-bit Suns, and 1-bit Suns.

The second win is that you can now specify the root window by name. 
(Either 'root' or 'X Root Window').

John Bradley - University of Pennsylvania - bradley@cis.upenn.edu

P.S.  I was going to submit a patch, but the patch wound up being
larger than the actual source code, so I'm just sending the whole
thing again.

-----------------------------------------------------------------------------
```
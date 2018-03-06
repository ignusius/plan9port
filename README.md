This is a port of many Plan 9 libraries and programs to Unix with my little fix.

Difference from plan9port
-------------------------

* Fix acme shortcut for linux
* Add ttf2subf and droid-sans fonts
* Testing only linux systems.

Installation
------------

To install, run ./INSTALL.  It builds mk and then uses mk to
run the rest of the installation.  

For more details, see install(1), at install.txt in this directory
and at https://9fans.github.io/plan9port/man/man1/install.html.

Documentation
-------------

See https://9fans.github.io/plan9port/man/ for more documentation.
(Documentation is also in this tree, but you need to run
a successful install first.  After that, "9 man 1 intro".)

Intro(1) contains a list of man pages that describe new features
or differences from Plan 9.

Helping out
-----------

If you'd like to help out, great!  The TODO file contains a small list.

If you port this code to other architectures, please share your changes
so others can benefit.

Git
---

You can use Git to keep your local copy up-to-date as we make 
changes and fix bugs.  See the git(1) man page here ("9 man git")
for details on using Git.

Note
------

Acme and fonts

You can use fontsrv, for example:
```
fontsrv -m ~/font/
acme  -f ~/font/Ubuntu/11a/font
```
or use Droid-sans font:
```
acme -f ~/plan9/font/droid/droid.14.font
```
or convert your lovely font and use it:
```
ttf2subf -s 14 -f example.ttf -n example -m antialias
acme -f ~/you/path/example/example.14.font
```



Contact
-------
* Maintainer this fork: Alexander Komarov <ignusius@gmail.com>

* Mailing list: https://groups.google.com/group/plan9port-dev
* Issue tracker: https://github.com/9fans/plan9port/issues
* Submitting changes: https://github.com/9fans/plan9port/pulls

* Russ Cox <rsc@swtch.com>

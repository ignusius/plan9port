This is a port of many Plan 9 libraries and programs to Unix with my little fix.

Difference from plan9port
-------------------------

* Fix acme shortcut for linux
* Add ttf2subf and droid-sans fonts
* Testing only linux systems.
* Add acme-golang addon [see here](src/cmd/acme/acme-addons/acme-golang/)

Installation
------------
For ubuntu 18.04 LTS:
```
sudo apt-get install gcc libxext-dev  libfontconfig-dev libxt-dev
```
Download

```
git clone https://github.com/ignusius/plan9port
```

To install, run ./INSTALL.  It builds mk and then uses mk to
run the rest of the installation.  

For more details, see install(1), at install.txt in this directory
and at https://9fans.github.io/plan9port/man/man1/install.html.

Add PATH in ~/.profile
```
export PLAN9="$HOME/plan9ports"
export PATH="$PATH:$PLAN9/bin"

```
Run acme!

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
## Shortcuts and commands
- `Edit =` find out the current line number 
- `:13` goto 13th line
- `:0` goto file beginning
- `:$` goto file end
- `:1,$` or `:,` or `Edit 1,$` or `Edit ,` select all lines
- `:1,5` or `Edit 1,5` select lines 1..5
- `Edit , d` clear window
- `Edit , < echo hello world` replace window body with some text
- `Edit , < erl -man maps` replace window body with erlang manual
- `Edit , s/text/TEXT/g` or `Edit , | sed 's/text/TEXT/g'` global replace
- `$%` or `$samfile` current file name
- `$winid` current window id
- `echo some text | 9p write acme/$winid/body` append to the end of current window
- keyboard shortcuts:
  - `ctrl-c` copy (snarf)
  - `ctrl-v` paste
  - `ctrl-z` undo
  - `ctrl-y` redo
  - `ctrl-g` get (Get command)
  - `ctrl-s` put (Put command)
  - `ctrl-u` delete from cursor to start of line
  - `ctrl-w` delete word before the cursor
  - `ctrl-h` delete character before the cursor
  - `ctrl-a` move cursor to start of the line
  - `ctrl-e` move cursor to end of the line
  - `ctrl-i` tab
  - `ctrl-j` enter
  - `ctrl-f` filepath autocompletion
- search with right click:
  - `:+/foobar`, `:/foobar` and just `foobar` search forward
  - `:-/foobar` search backwards
- press `esc` to select the last typed text
- press `esc` again to delete any selected text
- `Font` switch between fonts
- `:/^hel` regexp match: lines starting with 'hel'
- `:/lo\n/` regexp match: lines ending with 'lo' 
- `:/^b/,/^e/` regexp match: lines between starting with 'b' and starting with 'e'
- `Dump` write the state of acme to the file
- `Load` restore from the dump
- `Edit , > python` pipe window body through python interpreter

## Sam commands

- `Edit +/hello` search 'hello' forward
- `Edit -/hello` search 'hello' backward
- `Edit , > wc -l` count lines in file
- `Edit , | sort` sort lines
- `Edit 3,5p` print lines 3..5 in new window
- `Edit 3,5 | upper` lines 3..5 upper cased
- `Edit 3,5 s/HE/he/g` replace on 3..5 lines only 
- `Edit 2 d` delete 2nd line
- `Edit 2 c/new` change 2nd line
- `Edit 2 a/new` append text after 2nd line
- `Edit 2 i/new` insert text before 2nd line
- `Edit 2 < date` replace 2nd line with the output of date
- `Edit ,x/^TODAY$/ < date` replace matching lines with the output of date
- `Edit ,x/Plan9/ |tr a-z A-Z` replace all instances of Plan9 with upper case
- `Edit 3,5x/^/ a/	/` indent lines 3..5 with 1 tab



Contact
-------
* Maintainer this fork: Alexander Komarov <ignusius@gmail.com>

* Mailing list: https://groups.google.com/group/plan9port-dev
* Issue tracker: https://github.com/9fans/plan9port/issues
* Submitting changes: https://github.com/9fans/plan9port/pulls

* Russ Cox <rsc@swtch.com>

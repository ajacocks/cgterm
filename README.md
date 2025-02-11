CGTerm - a platform independent C/G terminal
================================================

As the title says, CGTerm is an open source, platform independent
terminal program for C/G telnet BBS:s. It's supposed to compile and
run on any POSIX compliant OS with the SDL library installed.

Installation (UNIX)
-------------------

First, download and install the [SDL library](http://www.libsdl.org/download-1.2.php)
if it's not included with your OS.

Edit the supplied `Makefile` as needed, then run `make`, and `make install`.

Installation (Mac OS)
-------------------

As above, cgterm requires SDL. To install SDL, you can use either [Homebrew](https://brew.sh/) or [MacPorts](https://www.macports.org/), or compile it yourself. You will also need the Xcode command-line tools.

Next, edit `Makefile`, and specify the correct destination directory, as per the comment in the file. Last, run `make`, and `make install`.

Usage
-----

    cgterm [-d delay] [-f] [-k keyboard.kbd] [-o logfile] [-r seconds]
    [-s] [-z zoom] [host [port]]

CGTerm looks for options in the following order: first it uses
anything specified on the command line, then it tries to read options
from a file called `.cgtermrc` in your home directory, and if that fails
it tries to read from the system configuration file. The available
options are:

Config Key  | Switch  | Action
------------|---------|-------------------------------------------------------------------
senddelay   | -d      | Delay between sent characters in milliseconds (default: 0)
fullscreen  | -f      | Fullscreen mode
keyboard    | -k      | Select keyboard configuration file (default: `keyboard.kbd`)
logfile     | -o      | Save window output
zoom        | -z      | Window zoom factor (default: 2)
reconnect   | -r      | Reconnect if disconnected within N seconds (default: 0 = off)
host        | 1st arg | Host to connect to
port        | 2nd arg | Port to connect to (default: 23)
localecho   |         | Enable local echo (default: no)
sound       | -s      | Enable sound playback (default: yes)
columns     | -4/-8   | 40 or 80 columns (default: 40)
xferdir     |         | Path to where you want to save file downloads.
bookmark    |         | Add a host to the bookmark menu. Use the format alias, host, port.

Hotkeys
-------

Certain program functions can be activated with hotkeys. These are
bound to the Meta key (a.k.a. Command key) plus another key. You can
also bring up a menu with Escape.

Key | Action
----|--------------------------------
A   | Abort loading or macro playback
B   | Open bookmarks
C   | Start/stop recording macro
D   | Connect/disconnect
E   | Toggle local echo
F   | Toggle fullscreen mode
I   | Set transfer dir or disk image
L   | Load SEQ file
Q   | Quit CGTerm
R   | Reconnect to last host
S   | Save screenshot to SEQ file
T   | Transfer files
V   | Play recorded macro
Alt | Toggle lower/upper case font

The scrollback buffer can be accessed with the Page Up and Page Down
keys.

Keyboards
---------

(If you're a Windows user, you can skip this section - it's only for
Unix and Mac users).

As modern keyboards differ quite radically from the C64's, keys need
to be remapped. To make our lives even more difficult, different
countries have different keyboard layouts. The SDL library makes most
of this transparent, but not everything, so you need to supply a
keyboard configuration file. A couple of configuration files are
included with the source. If one of those works for you, simply edit
the config file and CGTerm will use it automatically. If you're not so
lucky, you'll need to create your own. The configuration file contains
two columns: a named C64 key to the left, and a keysym number to the
right. To find out the keysym number of a key, use the supplied
`testkbd` program. Just hit a key and it'll print the keysym for
you. Once you've created a working configuration, please send it to me
so that I can include it in the next update.

File Transfer
-------------

CGTerm can receive files with the following protocols:

* Punter
* Xmodem
* Xmodem/CRC
* Xmodem-1k

and it can upload files with the following protocols:

* Xmodem
* Xmodem/CRC
* Xmodem-1k

Acknowledgements
----------------

Thanks to David Holz, Ullrich von Bassewitz, and Morphfrog for source
patches. Thanks to Taper/3AD for running a BBS that makes it all worth
it. Thanks also to all the beta testers.

CGChat - a platform independent 64CHAT client
=================================================

As the title says, CGChat is an open source, platform independent
client for 64CHAT. It's supposed to compile and run on any POSIX
compliant OS with the SDL library installed.

Installation (UNIX)
-------------------

First, download and install the [SDL library](http://www.libsdl.org/download-1.2.php)
if it's not included with your OS.

Edit the supplied `Makefile` as needed, then run `make`, and `make install`.

Usage
-----

    cgchat [-4|-8] [-f] [-k keyboard.kbd] [-s] [-z zoom] [host [port]]

CGChat looks for options in the following order: first it uses
anything specified on the command line, then it tries to read options
from a file called `.cgchatrc` in your home directory, and if that fails
it tries to read from the system configuration file. The available
options are:

Config Key  | Switch  | Action
------------|---------|-------------------------------------------------------------------
fullscreen  | -f      | Fullscreen mode
keyboard    | -k      | Select keyboard configuration file (default: `keyboard.kbd`)
zoom        | -z      | Window zoom factor (default: 2)
reconnect   | -r      | Reconnect if disconnected within N seconds (default: 0 = off)
host        | 1st arg | Host to connect to
port        | 2nd arg | Port to connect to (default: 23)
sound       | -s      | Enable sound playback (default: yes)
columns     | -4/-8   | 40 or 80 columns (default: 40)
bookmark    |         | Add a host to the bookmark menu. Use the format alias, host, port.

Hotkeys
-------

Certain program functions can be activated with hotkeys. These are
bound to the Meta key (a.k.a. Command key) plus another key. You can
also bring up a menu with Escape.

Key | Action
----|--------------------------------
A   | Abort loading or macro playback
B   | Open bookmarks
C   | Start/stop recording macro
D   | Connect/disconnect
F   | Toggle fullscreen mode
L   | Load SEQ file
Q   | Quit CGTerm
R   | Reconnect to last host
S   | Save screenshot to SEQ file
V   | Play recorded macro
Alt | Toggle lower/upper case font

The scrollback buffer can be accessed with the Page Up and Page Down
keys.

Keyboards
---------

See the CGTerm documentation.

Contact
-------

You can email me at MagerValp@cling.gu.se.

License
-------

CGTerm is released under a slightly modified BSD license:

Copyright (c) 2003, Per Olofsson
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

* Redistributions of source code must retain the above copyright
  notice, this list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above
  copyright notice, this list of conditions and the following
  disclaimer in the documentation and/or other materials provided
  with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

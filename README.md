# SzimatSzatyor
SzimatSzatyor is a WoW (World of Warcraft) injector sniffer written in C++.

[![Poll: Do you like to sniff WoW with SzimatSzatyor?](http://i.imgur.com/z4bqVFXl.png)](http://pollabout.com/#/polls/c00408)

A sniffer can log packets which sended by the server and which sended by
the client also. The code using a lot of low-level C Windows API.

Some words about the project name: szimatszatyor is a
hungarian compound word, in English "szimat" should be "sniff" or "flair" and
"szatyor" should be "bag". This project is a sniffer so that's why I named it
to szimatszatyor because of the szimat =~ sniff. By the way szimatszatyor is
a bag where gas mask is stored (so gas mask bag) and nowadays it's a
fashionable bag which weared by some people.
A picture of szimatszatyor: http://i.imgur.com/5elL0T9.jpg

Basically szatyor.exe is the injector which injects the DLL (szatyor.dll)
into the client process and szatyor.dll is the sniffer which sniffs the
packets from the client.

## Features
* Can target specific WoW clients by name (default is Wow.exe and WowB.exe) via pass an argument to the injector,
usage: ```szatyor.exe [wow_exe_name]```
* Can detect the targeted WoW process build number so supports multiple builds.
* Can detect if multiple processes have the same name (which should be injected) and gives choice which should be injected.
* Can detect if a process is already injected.
* Dumps packets to a binary file which is can be parsed by TrinityCore's WowPacketParser which is
available at here: https://github.com/TrinityCore/WowPacketParser
* Dumps packets to a "user friendly" log file which makes possible to read the packets without parsing them.
This feature is disabled by default. Read the "Usage" section to know how to enable it.

## Usage
* You need szatyor.exe (the injector) and szimat.dll (the sniffer) in the same directory.
Note: like other (most) sniffers this directory can be different than WoW's directory.
* Start szatyor.exe Note: the user which started WoW should start that too, of course admin user is also OK but not needed.
* That's all. You can start SzimatSzatyor at anytime.
* If you want to close the sniffer just press CTRL-C or close the WoW. Note: CTRL-C works only in fullscreen mode.
* Log files are created to where SzimatSzatyor is.
* Create an empty file (name: dump_user_friendly) where the SzimatSzatyor is to enable the "user friendly" log format.
Just delete (or rename) this file if you want to disable it again. You can NOT enable or disable while WoW is running.

## Supported clients
* Classic/Vanilla: 5875
* The Burning Crusade: 8606
* Wrath of the Lich King: 12340
* Cataclysm: 13623, 15595
* Mists of Pandaria: 16135, 16357, 16650, 16709, 16826, 16981, 16983, 16992, 17055, 17056, 17093, 17116, 17124, 17128, 17359,
17371, 17399, 17538, 17658, 17688, 17859, 17889, 17898, 17930, 17956, 18019, 18291, 18414
* Warlords of Draenor: 18379, 18443, 18471, 18482, 18505

## Warning
An injector sniffer (like SzimatSzatyor) is writing into WoW's memory at runtime so Warden (anti-cheating tool in WoW) **can** detect it.
At this time never detected by Warden and no punishment rewarded.
I think Blizzard just doesn't care about it, it's not really a cheat... :)

## Compilation
If you want to compile SzimatSzatyor from the source code you have to generate the project files for your compiler with CMake.

CMake (http://www.cmake.org/) is an extensible, open-source system that manages the build process in an operating system
and in a compiler-independent manner. You can download a GUI for your Windows OS and generate project files for example
your Visual Studio.

Note that you must compile the project with a 32-bit compiler because the sniffer won't work if you compile it in 64-bit mode.

Source code is available at: http://github.com/Anubisss/SzimatSzatyor

Compiled binaries: http://github.com/Anubisss/SzimatSzatyor/wiki/Download

Screenshots: http://github.com/Anubisss/SzimatSzatyor/wiki/Screenshots

## License: GNU GPLv3
COPYING file contains the license which should be distributed with the software or visit http://www.gnu.org/licenses/gpl-3.0.html

SzimatSzatyor is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

SzimatSzatyor is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with SzimatSzatyor.  If not, see <http://www.gnu.org/licenses/>.

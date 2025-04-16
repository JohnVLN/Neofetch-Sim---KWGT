## Neofetch style widget for KWGT ✨
Using the popular [Neofetch](https://github.com/dylanaraps/neofetch) info tool as inspiration for a widget.

#### Formula for requesting phone information:
``` kustom
[c=#00FF00]OS[/c]: Android $sh("getprop ro.build.version.release")$ $sh("uname -m")$
[c=#00FF00]Host[/c]: $si(man)$ $si(model)$
[c=#00FF00]Resolution[/c]: $si(swidth)*si(sdensity)$x$si(sheight)*si(sdensity)$
[c=#00FF00]DE[/c]: $si(lnchname)$
[c=#00FF00]Icons[/c]: Nova Dark
[c=#00FF00]CPU[/c]: $sh("cat /proc/cpuinfo | grep Hardware | sed 's/.*: //' | sed 's/Technologies, Inc.//'")$ @ $rm(fmax)$Mhz
[c=#00FF00]Memory[/c]: $rm(mused)$Mb / $rm(mtot)$Mb
[c=#00FF00]Disk[/c]: $mu(ceil, rm(fsfree, int)/1000)$Gb / $mu(ceil, rm(fstot, int)/1000)$Gb
```
Formulas got from [this Reddit thread](https://www.reddit.com/r/unixporn/comments/1ecf3hq/oc_custom_neofetch_widget_that_updates_in_real/).

#### Music player info:
``` kustom
[c=#00FF00]<player>[/c] $mi(package)$
$mi(title)$ --- $mi(artist)$
[c=#00FF00]$mi(state)$[/c] @ Speaker Module: $if(nc(aname, 0) = "", "Device", "[c=#00FF00]" + nc(aname, 0) + "[/c]")$
```
In the formula, `$if(nc(aname, 0) = "", "Device", "[c=#00FF00]" + nc(aname, 0) + "[/c]")$` will check for bluetooth devices (for speakers and wireless buds and headphones) , if nothing is connected, it will display "Device", if there is, it will display its name.

ASCII art in the image is the logo from Bungie's Marathon.
ASCII art from images can be made [here](https://www.asciiart.eu/image-to-ascii).
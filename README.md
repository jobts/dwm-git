# dwm-git
Dwm Arch Linux modified package


### Files added:

* config.dev.h.diff  - custom mod patch
* .xprofile   - autostart script, install needed apps, edit and copy it to your home dir

**patches that install from original src**
* https://dwm.suckless.org/patches/xtile/dwm-xtile-6.2.diff
* https://dwm.suckless.org/patches/systray/dwm-systray-6.2.diff
* https://dwm.suckless.org/patches/pertag/dwm-pertag-20170513-ceac8c9.diff
* https://dwm.suckless.org/patches/autoresize/dwm-autoresize-20160718-56a31dc.diff
* https://dwm.suckless.org/patches/gaplessgrid/dwm-gaplessgrid-20160731-56a31dc.diff
* https://dwm.suckless.org/patches/cyclelayouts/dwm-cyclelayouts-20180524-a09e766.diff
* ~~https://dwm.suckless.org/patches/bottomstack/dwm-bottomstack-6.1.diff~~ removed, conflict with xtile
* ~~https://dwm.suckless.org/patches/centeredmaster/dwm-centeredmaster-6.1.diff~~ removed, conflict with xtile


## Installation

Download / git clone package

### Icons font, added to depends

~~pacman -S  awesome-terminal-fonts~~


### rofi app menu, added to depends

~~pacman -S rofi~~



### Build, install package
```
makepkg -si
```

### reinstall
```
makepkg -Cfi
```

or you can download original sources and apply patches,  see PKGBUILD file

### .xprofile file
The working sample is included to the package. Install optional dependencies and copy .xprofile to your home dir.

## Win key as Modkey. General keyboard shortcuts available.
### New keybord shortcuts:
 *  Win - Arrow keys duplicates hjkl
 *  Volume keys:  Win - numpad + / Win- numpad  Pulseaudio controls
 *  Alt + F4 close window as usual
 *  Alt + F2 app menu duplicate
 *  Win + g gaplessgrid
 *  Win + Ctrl + l  - light-dm lock screen
 *  Win + Ctrl + , / Win + Ctrl + .   Layouts loop
 *  Win + `  (tilda)  open terminal
### Xtile shortcuts in tile mode:
 *  Win + r  - Global rotate widows
 *  Win + Ctrl + r - Master
 *  Win + Shift + r - Stack
 *  Win + Ctrl + Shift + r - All three areas simultaneously


### Layouts:

*  { "[]=",      tile },    first entry is default
*  { "><>",      NULL },    no layout function means floating behavior
*  { "[M]",      monocle },
*  { "###",      gaplessgrid }

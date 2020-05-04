# dwm-git
Dwm Arch Linux modified package


### Files added:

* config.dev.h.diff  - mod patch
* .xprofile   - autostart script, install needed apps, edit and copy it to your home dir

**patches that install from original src**

* ~~https://dwm.suckless.org/patches/systray/dwm-systray-6.2.diff~~ disabled until fix
* https://dwm.suckless.org/patches/pertag/dwm-pertag-20170513-ceac8c9.diff
* https://dwm.suckless.org/patches/autoresize/dwm-autoresize-20160718-56a31dc.diff

**patches included in config.dev.h**
* https://dwm.suckless.org/patches/gaplessgrid/dwm-gaplessgrid-20160731-56a31dc.diff
* https://dwm.suckless.org/patches/bottomstack/dwm-bottomstack-6.1.diff
* https://dwm.suckless.org/patches/centeredmaster/dwm-centeredmaster-6.1.diff
* https://dwm.suckless.org/patches/cyclelayouts/dwm-cyclelayouts-20180524-a09e766.diff

**dwm-systray mod
* dwm-systray-6.2-20200504.diff

## Installation 

Download / git clone package

### Icons font, added to depends
```
~~pacman -S  awesome-terminal-fonts~~
```

### rofi app menu, added to depends
```
~~pacman -S rofi~~
```


### Build, install package
```
makepkg -si
```

### reinstall 
```
makepkg -Cfi
```

or you can download original sources and apply patches,  see PKGBUILD file

## .xprofile file
### The working sample is included to the package. Install optional dependencies and copy .xprofile to your home dir.

## Win key as Modkey. General keyboard shortcuts available.
### New keybord shortcuts:
 *  Win - Arrow keys duplicates hjkl
 *  Volume keys:  Win - numpad + / Win- numpad  Pulseaudio controls
 *  Alt + F4 close window as usual
 *  Alt + F2 app menu duplicate
 *  Win + g gaplessgrid
 *  Win + u bstack
 *  Win + o bstackhoriz
 *  Win + Ctrl + l  - light-dm lock screen
 *  Win + Ctrl + , / Win + Ctrl + .   Layouts loop
 *  Win + `  (tilda)  open terminal
 *  Win + c - centeredmaster
 *  Win + v - centeredfloatingmaster

 
### Layouts: 

*  { "[]=",      tile },    first entry is default
*  { "><>",      NULL },    no layout function means floating behavior
*  { "[M]",      monocle },
*  { "###",      gaplessgrid },
*  { "TTT",      bstack },
*  { "===",      bstackhoriz },
*  { "|M|",      centeredmaster },
*  { ">M>",      centeredfloatingmaster },

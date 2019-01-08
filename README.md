# dwm-git
Dwm Arch Linux modified package


### Files added:

* config.dev.h.diff  - mod patch
* .xprofile   - autostart script, install needed apps, edit and copy it to your home dir

**patches that install from original src**

* https://dwm.suckless.org/patches/systray/dwm-systray-20180314-3bd8466.diff
* https://dwm.suckless.org/patches/pertag/dwm-pertag-20170513-ceac8c9.diff
* https://dwm.suckless.org/patches/autoresize/dwm-autoresize-20160718-56a31dc.diff

**patches included in config.dev.h**

* https://dwm.suckless.org/patches/gaplessgrid/dwm-gaplessgrid-20160731-56a31dc.diff
* https://dwm.suckless.org/patches/bottomstack/dwm-bottomstack-6.1.diff
* https://dwm.suckless.org/patches/centeredmaster/dwm-centeredmaster-6.1.diff
* https://dwm.suckless.org/patches/cyclelayouts/dwm-cyclelayouts-20180524-a09e766.diff


## Installation 

Download / git clone package

### Icons font
```
pacman -S  awesome-terminal-fonts
```

### rofi app menu
```
pacman -S rofi
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


## Win key as Modkey
### Keybord shortcuts:
 *  Win - Arrow keys duplicates hjkl
 *  Volume keys:  Win - numpad + / Win- numpad  Pulseaudio controls
 *  Alt + F4 close window as usual
 *  Alt + F2 close window as usual
 *  Win + backstick (tilda)  open terminal
 *  Win + g gaplessgrid
 *  Win + u bstack
 *  Win + o bstackhoriz
 *  Ctrl + Win + l  - light-dm lock screen
 *  Win + , / Win + . loop layots
 *  Win + `  tilda open terminal
 
### Layouts: 

*  { "[]=",      tile },    first entry is default
*  { "><>",      NULL },    no layout function means floating behavior
*  { "[M]",      monocle },
*  { "###",      gaplessgrid },
*  { "TTT",      bstack },
*  { "===",      bstackhoriz },
*  { "|M|",      centeredmaster },
*  { ">M>",      centeredfloatingmaster },
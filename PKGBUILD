pkgname=dwm-git
_pkgname=dwm
pkgver=6.2.5.gf09418b
pkgrel=1
pkgdesc="A dynamic window manager for X"
url="http://dwm.suckless.org"
arch=('i686' 'x86_64')
license=('MIT')
options=(zipman)
depends=('libx11' 'libxinerama' 'libxft')
makedepends=('git')
install=dwm.install
provides=('dwm')
conflicts=('dwm')
epoch=1
source=(dwm.desktop
        "$_pkgname::git+http://git.suckless.org/dwm")
md5sums=('939f403a71b6e85261d09fc3412269ee'
         'SKIP')

pkgver(){
  cd $_pkgname
  git describe --tags |sed 's/-/./g'
}

prepare() {
  PURL="https://dwm.suckless.org/patches/pertag/dwm-pertag-6.2.diff
  https://dwm.suckless.org/patches/autoresize/dwm-autoresize-20160718-56a31dc.diff"
  # removed until fixing, custom created https://dwm.suckless.org/patches/systray/dwm-systray-6.2.diff
  # conflict https://dwm.suckless.org/patches/pertag/dwm-pertag-20170513-ceac8c9.diff
  # zero byte, check later https://dwm.suckless.org/patches/winview/dwm-6.1-winview.diff
  # conflict with systray https://dwm.suckless.org/patches/alpha/dwm-alpha-20180613-b69c870.diff
  # very old https://dwm.suckless.org/patches/viewontag/dwm-r1522-viewontag.diff
  # very old https://dwm.suckless.org/patches/xtile/dwm-6.0-xtile.diff

  # custom systray
  patch -p1 -d $_pkgname < ../dwm-systray-6.2-20200504.diff

  for i in $PURL; do
    curl -O "$i"
    file=$(echo  "$i" | rev |  cut -d "/" -f 1 | rev)
    echo -e "------------------------\napply patch $file\n-------------------------"
    patch -p1 -d $_pkgname < $file
  done

  echo "Apply Custom config and patches"
  # included in config:
  # https://dwm.suckless.org/patches/gaplessgrid/dwm-gaplessgrid-20160731-56a31dc.diff
  # https://dwm.suckless.org/patches/bottomstack/dwm-bottomstack-6.1.diff
  # https://dwm.suckless.org/patches/centeredmaster/dwm-centeredmaster-6.1.diff
  # https://dwm.suckless.org/patches/cyclelayouts/dwm-cyclelayouts-20180524-a09e766.diff
  patch -p1 -d $_pkgname < ../config.dev.h.diff

  cd $_pkgname
  if [[ -f "$SRCDEST/$pkgname/config.h" ]]; then
    cp -f "$SRCDEST/$pkgname/config.h" config.h
  fi
}

build() {
  cd $_pkgname
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd $_pkgname
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -m644 -D README "$pkgdir/usr/share/doc/$pkgname/README"
  install -m644 -D ../dwm.desktop "$pkgdir/usr/share/xsessions/dwm.desktop"
}

# vim:set ts=2 sw=2 et:

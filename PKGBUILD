# Maintainer: Alexander Milchinskiy <milchinskiy@gmail.com>

pkgname=st-flexipatch
pkgver=0.9
pkgrel=14
pkgdesc="st is a simple terminal implementation for X"
url="https://st.suckless.org/"
arch=('i686' 'x86_64')
license=('MIT')
options=('zipman')
depends=('libxft')
makedepends=('ncurses' 'libxext' 'git')
optdepends=('dmenu: feed urls to dmenu')

prepare() {
  cd ..
  make clean
  rm -f config.h patches.h
}

build() {
  cd ..
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd ..
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname"/LICENSE
  install -m644 -D README "$pkgdir/usr/share/doc/$pkgname"/README
}

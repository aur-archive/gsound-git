# Maintainer: Yosef Or Boczko <yoseforb@gnome.org>

_pkgname=gsound
pkgname=$_pkgname-git
pkgver=1.0.1
pkgrel=1
_realver=1.0.1
pkgdesc="GObject library for playing system sounds"
arch=(i686 x86_64)
license=('LGPLv2.1+')
url="https://git.gnome.org/browse/gsound/tree/"
depends=("glib2" "libcanberra")
makedepends=('vala' 'git' 'gtk-doc' 'gnome-common')
options=('!libtool' '!emptydirs')
conflicts=('gsound')
replaces=('gsound')
provides=("gsound=$_realver")
source=('git://git.gnome.org/gsound')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  git describe --always | sed 's|-|.|g'
}

prepare() {
  cd "$srcdir/$_pkgname"
}

build() {
  cd "$srcdir/$_pkgname"
  ./autogen.sh --prefix=/usr --disable-static --enable-gtk-doc
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make DESTDIR="${pkgdir}" install
}

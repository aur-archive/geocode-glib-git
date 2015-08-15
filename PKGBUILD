# Contributor: Yosef Or Boczko <yoseforb@gnome.org>

_pkgname=geocode-glib
pkgname=$_pkgname-git
pkgver=3.11.5
_realver=3.11.5
pkgrel=1
pkgdesc="Geocode Helper library"
arch=(i686 x86_64)
license=('GPL')
url="https://git.gnome.org/browse/geocode-glib/"
depends=('glib2' "json-glib>=0.16.2" 'libsoup')
makedepends=('intltool' 'gobject-introspection' 'gtk-doc' 'gnome-common')
options=('!libtool' '!emptydirs')
conflicts=('geocode-glib')
replaces=('geocode-glib')
provides=("geocode-glib=${_realver}")
source=('git://git.gnome.org/geocode-glib')
sha256sums=('SKIP')

 pkgver() {
  cd "$srcdir/$_pkgname"
  git describe --always | sed 's/-/./g'
}

build() {
  cd "$srcdir/$_pkgname"
  ./autogen.sh --prefix=/usr --enable-introspection --enable-gtk-doc
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make DESTDIR="${pkgdir}" install
}

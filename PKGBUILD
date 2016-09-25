# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgname=yelp-tools
pkgver=3.18.0+1+g193c2bd
pkgrel=1
pkgdesc="Collection of tools for building and converting documentation"
url="https://git.gnome.org/browse/yelp-tools"
arch=(any)
depends=(yelp-xsl libxslt libxml2 itstool)
makedepends=(git)
license=(GPL)
_commit=193c2bd0b4d9e80344184e3f14b21c4a5296701c
source=("git://git.gnome.org/yelp-tools#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
  cd $pkgname
  git describe --tags | sed 's/-/+/g'
}
prepare() {
  cd $pkgname
  NOCONFIGURE=1 ./autogen.sh
}

build() {
  cd $pkgname
  ./configure --prefix=/usr
  make
}

package() {
  cd $pkgname
  make DESTDIR="$pkgdir" install
}

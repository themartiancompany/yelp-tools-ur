# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgname=yelp-tools
pkgver=3.27.90
pkgrel=1
pkgdesc="Collection of tools for building and converting documentation"
url="https://git.gnome.org/browse/yelp-tools"
arch=(any)
depends=(yelp-xsl libxslt libxml2 itstool docbook-xsl)
makedepends=(git)
license=(GPL)
_commit=c0e9669fbbeddbeac7dd3778abfbbd68d85d93ba  # tags/3.27.90^0
source=("git+https://git.gnome.org/browse/yelp-tools#commit=$_commit")
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

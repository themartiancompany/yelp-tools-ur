# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgname=yelp-tools
pkgver=3.3.4
pkgrel=1
pkgdesc="Tools for creating Yelp documentation"
arch=('any')
depends=('yelp-xsl' 'libxslt' 'libxml2' 'itstool')
license=('GPL')
options=('!emptydirs' '!libtool')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.xz)
sha256sums=('7c22b5e96709da2129c3cb982cffbc8129deb6d7b32684db64d1cfd514bddcab')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}

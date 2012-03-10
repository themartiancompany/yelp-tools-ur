# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgname=yelp-tools
pkgver=3.3.3
pkgrel=1
pkgdesc="Tools for creating Yelp documentation"
arch=('any')
depends=('yelp-xsl' 'libxslt' 'libxml2' 'itstool')
license=('GPL')
options=('!emptydirs' '!libtool')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.xz)
sha256sums=('072ce2db79517c3875dbb1884e51e700d3053084b9a27310b676e30fd8a1e087')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}

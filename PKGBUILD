# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgname=yelp-tools
pkgver=3.9.90
pkgrel=1
pkgdesc="Tools for creating Yelp documentation"
arch=('any')
depends=('yelp-xsl' 'libxslt' 'libxml2' 'itstool')
license=('GPL')
options=('!emptydirs' '!libtool')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.xz)
sha256sums=('0c4b84cc33806570c7d745807ca881638d6bff6c8034ce775b0475a9f5078137')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}

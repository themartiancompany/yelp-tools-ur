# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgname=yelp-tools
pkgver=3.6.1
pkgrel=1
pkgdesc="Tools for creating Yelp documentation"
arch=('any')
depends=('yelp-xsl' 'libxslt' 'libxml2' 'itstool')
license=('GPL')
options=('!emptydirs' '!libtool')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.xz)
sha256sums=('5226e8245bb87f10e485aa65f5bf18d9e4fb5ef82f2e3c3734dd91bdf6f5c19a')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}

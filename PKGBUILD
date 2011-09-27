# Maintainer: Jan de Groot <jgc@archlinux.org>

pkgname=yelp-tools
pkgver=3.2.0
pkgrel=1
pkgdesc="Tools for creating Yelp documentation"
arch=('any')
depends=('yelp-xsl' 'libxslt' 'libxml2' 'itstool')
license=('GPL')
options=('!emptydirs' '!libtool')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.xz)
sha256sums=('45038c909ec50d9656745d4668cba964247e204e85bd75c6e78e4a9bc7729f9a')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}

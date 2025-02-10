# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Brett Cornwall <ainola@archlinux.org>
# Maintainer: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# Contributor: Jan de Groot <jgc@archlinux.org>

_py="python"
_proj="gnome"
_pkg="yelp"
_component="tools"
pkgname="${_pkg}-${_component}"
pkgver=42.1
pkgrel=2
_pkgdesc=(
  "Collection of tools for"
  "building and converting"
  "documentation."
)
pkgdesc="${_pkgdesc[*]}"
_http="https://gitlab.${_proj}.org"
_ns="GNOME"
url="${_http}/${_ns}/${pkgname}"
arch=(
  'any'
)
depends=(
  'yelp-xsl'
  "${_py}-lxml"
  'itstool'
  'libxml2'
  'docbook-xsl'
  'mallard-ducktype'
)
makedepends=(
  'git'
  'meson'
)
license=(
  "GPL"
)
_commit="fe5ff72ca46fba425143e5dc67d660703c86145f"  # tags/42.1^0
source=(
  "git+${url}.git#commit=${_commit}"
)
sha256sums=(
  'SKIP'
)

pkgver() {
  cd \
    "${pkgname}"
  git \
    describe \
    --tags | \
    sed \
      's/[^-]*-g/r&/;s/-/+/g'
}

prepare() {
  cd \
    "${pkgname}"
}

build() {
  local \
    _meson_opts=()
  _meson_opts=(
    -D help="true"
  )
  arch-meson \
    "${pkgname}" \
    build \
    "${_meson_opts[@]}"
  meson \
    compile \
    -C \
      "build"
}

check() {
  meson \
    test \
    -C \
      "build" \
      --print-errorlogs
}

package() {
  meson \
    install \
    -C \
      "build" \
      --destdir \
        "${pkgdir}"
}

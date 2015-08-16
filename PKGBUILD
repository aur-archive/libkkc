# Maintainer: ponsfoot <cabezon dot hashimoto at gmail dot com>

pkgname=libkkc
pkgver=0.2.4
pkgrel=1
pkgdesc="Japanese Kana Kanji conversion library"
arch=('i686' 'x86_64')
url="https://bitbucket.org/libkkc"
license=('GPL')
options=(!libtool)
depends=('libkkc-data' 'skk-jisyo' 'marisa' 'json-glib' 'libgee06')
makedepends=('vala0.18' 'pkg-config' 'gobject-introspection' 'marisa-python2')
changelog=ChangeLog
source=(https://bitbucket.org/libkkc/libkkc/downloads/${pkgname}-${pkgver}.tar.gz)
sha1sums=('28bafb612f8176735f02bd6f49581e072700af4e')

build() {
  cd "${pkgname}-${pkgver}"

  VALAC=/usr/bin/valac-0.18 \
  PYTHON=/usr/bin/python2 \
  ./configure --prefix=/usr --disable-static --disable-silent-rules
  make
}

package() {
  cd "${pkgname}-${pkgver}"
  make DESTDIR="$pkgdir" install
  install -d "${pkgdir}/usr/share/doc/${pkgname}-${pkgver}"
  install -m 644 README data/rules/README.rules COPYING \
    "${pkgdir}/usr/share/doc/${pkgname}-${pkgver}/"  
}

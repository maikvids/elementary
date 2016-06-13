pkgname=elementary
pkgver=1.17.1
pkgrel=1
pkgdesc="Enlightenment's widget set"
arch=('x86_64')
url="http://www.enlightenment.org"
license=('BSD')
depends=('efl' 'evas_generic_loaders')
makedepends=('doxygen' 'imagemagick' 'texlive-core' 'ghostscript')
source=(http://download.enlightenment.org/rel/libs/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('5d5e3ee47b5f99405527f330f23f8862')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  export CFLAGS="$CFLAGS -fvisibility=hidden"

  ./configure \
    --prefix=/usr \
    --disable-static
  make
}

package_elementary(){
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR=${pkgdir} install
}



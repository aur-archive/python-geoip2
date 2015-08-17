# $Id$
# Maintainer: Brett L Kleinschmidt <blk@blk.me>
# Contributor: Brett L Kleinschmidt <blk@blk.me>

pkgbase=python-geoip2
pkgname=('python-geoip2' 'python2-geoip2')
pkgver=2.0.0
pkgrel=1
pkgdesc="Python bindings for the GeoIP2 IP-to-country resolver library"
arch=('i686' 'x86_64')
url="https://pypi.python.org/pypi/geoip2"
license=('Apache')
makedepends=('python' 'python2')
source=(https://pypi.python.org/packages/source/g/geoip2/geoip2-${pkgver}.tar.gz)
md5sums=('499f7da6b7d0348193daae306d04174b')

prepare() {
  cp -a "geoip2-$pkgver"{,-py2}
}

build() {
  cd "geoip2-$pkgver"
  python setup.py build

  cd "../geoip2-$pkgver-py2"
  python2 setup.py build
}

package_python-geoip2() {
  depends=('python' 'python-maxminddb' 'python-requests>=2.2')

  cd "geoip2-$pkgver"
  python setup.py install --root="$pkgdir" -O1
}

package_python2-geoip2() {
  depends=('python2' 'python2-maxminddb' 'python2-requests>=2.2')

  cd "geoip2-$pkgver-py2"
  python2 setup.py install --root="$pkgdir" -O1
}

# vim:set ts=2 sw=2 et:

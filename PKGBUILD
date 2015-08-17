# Maintainer: Michael Schubert <mschu.dev at gmail>

pkgname=python2-pysundials
_pkgname=pysundials
pkgver=2.3.0_rc4
_pkgver=2.3.0-rc4
pkgrel=1
pkgdesc="A module containing python wrappers for the SUite of Non-linear DIfferential/ALgebraic Solvers (SUNDIALS)"
arch=('i686' 'x86_64')
depends=('python2' 'sundials23')
url="http://pysundials.sourceforge.net/"
license=('BSD')
source=("http://sourceforge.net/projects/pysundials/files/$_pkgname-$_pkgver.tar.gz" "config")
md5sums=('2e243e704cbe72803b62b4e87c72cf47'
         '880551f9fba1d77db7e5a3f7f77f7e69')

build() {
  cd "$srcdir/$_pkgname-$_pkgver"
  python2 setup.py build
}

package() {
  cd "$srcdir/$_pkgname-$_pkgver"
  python2 setup.py install --root="$pkgdir/" --skip-build --optimize=1
  pydir=`python2 -c "from distutils.sysconfig import get_python_lib; print get_python_lib()"`
  install -Dm644 ../config "$pkgdir/$pydir/$_pkgname/config"
}


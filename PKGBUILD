# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=orchid-demo
pkgname=orchid-demo
pkgver=0.0.6
pkgrel=3
pkgdesc="Haskell Wiki Demo"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-pipe<2.2' 'haskell-extensible-exceptions=0.1.1.1' 'haskell-mtl<1.2' 'haskell-network=2.2.1.7' 'haskell-orchid<0.1' 'haskell-salvia<0.2' 'haskell-salvia-extras<0.2' 'haskell-stm=2.1.2.1')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('72e6042ab456d5bd69175850e284b4d0')

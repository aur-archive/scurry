# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=Scurry
pkgname=scurry
pkgver=0.0.3
pkgrel=3
pkgdesc="A cross platform P2P VPN application built using Haskell."
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-binary>=0.4.3.1' 'haskell-bytestring=0.9.1.7' 'haskell-containers=0.3.0.0' 'haskell-network=2.2.1.7' 'haskell-network-bytestring>=0.1.1.2' 'haskell-parsec' 'haskell-random=1.0.0.2' 'haskell-stm=2.1.2.1' 'haskell-time=1.1.4' 'haskell-unix=2.4.0.2')
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
md5sums=('d0dffb97e1ce0f21d3c63cc85e9b8795')

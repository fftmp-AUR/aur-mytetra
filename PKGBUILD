# Maintainer: fft
# Contributor: cyberxndr <cyberxndr@gmail.com>

pkgname=mytetra-git
pkgver=1.44.160
pkgrel=1
pkgdesc="fftmp's git version of personal manager for data memorization and structuring notes"
arch=('x86_64')
url="https://github.com/fftmp-forked/mytetra_dev"
license=('GPL3')
depends=('hicolor-icon-theme' 'qt6-base')
makedepends=('qt6-tools')
optdepends=('mimetex: display TeX formulas')
source=("${pkgname}::git+https://github.com/fftmp-forked/mytetra_dev.git#branch=fft_fork")

sha256sums=('SKIP')

build(){
    cmake -DCMAKE_BUILD_TYPE=Release "${pkgname}"
    make
}


package(){
	make install DESTDIR="${pkgdir}"
}


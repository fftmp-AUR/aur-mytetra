# Maintainer: fft
# Contributor: cyberxndr <cyberxndr@gmail.com>

pkgname=mytetra
pkgver=1.44.232
pkgrel=1
pkgdesc="Personal manager for data memorization and structuring notes"
arch=('x86_64')
url="https://github.com/xintrea/mytetra_dev"
license=('GPL-3.0-only')
depends=('hicolor-icon-theme' 'qt5-base' 'qt5-svg')
source=(
  "https://github.com/xintrea/mytetra_dev/archive/refs/tags/v.${pkgver}.tar.gz"
  'p1.patch'
)

b2sums=(
  'a57d180c4ec53c751bff4ff7bb7d86e77a7081c451ea5fc2d72b0054fc906897c8ae369ada2f5c207180fc84e7971076bff12ec6d2665664c145ef9fa700cd21'
  'f86d56aaeb83a5a40f76b219e38352e91860c9dce06afa7bde9cb8342172a5c318f2424160deba48878dd983382a5edcae23178c0e301163ec7a128a85d3ddeb'
)

build(){
  cd "mytetra_dev-v.${pkgver}"
  patch thirdParty/mimetex/mimetex.c ../p1.patch
  sed -i 's/QMAKE_CFLAGS += -DAA/QMAKE_CFLAGS += -DAA -std=gnu17/' thirdParty/mimetex/mimetex.pro
  qmake
  make
}


package(){
  cd "mytetra_dev-v.${pkgver}/app"
  make install INSTALL_ROOT="${pkgdir}"
  mkdir -p "${pkgdir}/usr/bin/"
  mv "${pkgdir}/usr/local/bin/mytetra" "${pkgdir}/usr/bin/"
  rm -r "${pkgdir}/usr/local"
}


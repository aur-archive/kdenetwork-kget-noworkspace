# $Id: PKGBUILD 220402 2014-08-20 15:33:18Z svenstaro $
# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdenetwork-kget-noworkspace
pkgver=14.12.3
pkgrel=1
pkgdesc='Download Manager (without kdebase-workspace dependency)'
url='http://kde.org/applications/internet/kget/'
arch=('i686' 'x86_64')
license=('GPL' 'LGPL' 'FDL')
groups=('kde' 'kdenetwork')
depends=('kdebase-lib' 'kdebase-runtime' 'libktorrent' 'libmms')
makedepends=('cmake' 'automoc4' 'boost')
install=kdenetwork-kget.install
provides=('kdenetwork-kget')
conflicts=('kdenetwork-kget')
source=("http://download.kde.org/stable/applications/${pkgver}/src/kget-${pkgver}.tar.xz")
sha1sums=('e7a34241be366c38f8c0430119cc73f8bca21f4d')

prepare() {
  mkdir build
}

build() {
  cd build
  cmake ../kget-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DKDE4_BUILD_TESTS=OFF \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DWITH_NepomukCore=OFF \
    -DWITH_NepomukWidgets=OFF \
    -DWITH_KDE4Workspace=OFF
  make
}

package() {
  cd build
  make DESTDIR=$pkgdir install
}

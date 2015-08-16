# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=krunner
pkgver=4.99.0
pkgrel=1
pkgdesc='Framework for providing different actions given a string query'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/krunner'
license=('LGPL')
depends=('plasma-framework')
makedepends=('extra-cmake-modules' 'kdoctools')
groups=('kf5-aids')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/portingAids/${pkgname}-${pkgver}.tar.xz")
md5sums=('7cb6e42317fecf73a145229cba55778e')

prepare() {
  mkdir -p build
}

build() {
  export XDG_DATA_DIRS="/opt/kf5/share:$XDG_DATA_DIRS"

  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}

# Maintainer: Frank Krick frank.krick@gmail.com
pkgname=pmx-git
pkgver=0.0.1
pkgrel=1
pkgdesc="A performance mixer for music hardware"
arch=('x86_64')
url=
license=('GPL-3.0-only')
depends=(
  'pipewire>=1.2.7'
  'wireplumber>=0.5.7'
  'boost>=1.86.0'
  'grpc'
  'protobuf'
  'yaml-cpp>=0.8.0'
  'libsystemd')
makedepends=('meson')
source=(
  'git+https://github.com/performance-mixer/pwcpp.git'
  'git+https://github.com/performance-mixer/pmx.git'
  'git+https://github.com/performance-mixer/pmx-grpc.git')
md5sums=('SKIP' 'SKIP' 'SKIP')

build() {
  cd pmx
  meson setup build --prefix /usr --optimization 3 --buildtype release
  cd build
  meson compile
}

package() {
  cd pmx/build
  meson install --destdir "$pkgdir"
}

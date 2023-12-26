pkgname=usbredir
pkgver=0.13.0
pkgrel=1
pkgdesc='Libraries and utilities for redirecting USB devices to other machines'
arch=('x86_64')
url='https://gitlab.freedesktop.org/spice/usbredir'
license=('GPL-2' 'LGPL-2.1')
depends=()
makedepends=('meson')
source=("https://www.spice-space.org/download/usbredir/usbredir-${pkgver}.tar.xz")
sha512sums=('dd27b1794233d4a278c3ca0e2a1ef9518946d8c7422cf58bb83d8ed5b4358133da27bdb0f44ad7b679a9983b3c419c3ab014486735614f7ceea85bfa62904273')
src_name="usbredir-${pkgver}"

build() {
    cd "${src_name}"
    meson setup build --prefix=/usr
    cd build
    meson compile
}

package() {
    cd "${src_name}/build"
    DESTDIR=${pkgdir} meson install
}

pkgname=usbredir
pkgver=0.14.0
pkgrel=1
pkgdesc='Libraries and utilities for redirecting USB devices to other machines'
arch=('x86_64')
url='https://gitlab.freedesktop.org/spice/usbredir'
license=('GPL-2' 'LGPL-2.1')
depends=()
makedepends=('meson')
source=("https://www.spice-space.org/download/usbredir/usbredir-${pkgver}.tar.xz")
sha512sums=('8e8e8f1cdcf2285ebe24d45dac4d85f7ebe884bad890ffca51b963bfeb51cc26325d1029d0863fb14b925e9919858babdde2a509d570c0a8515bbe7f4dda94e4')
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

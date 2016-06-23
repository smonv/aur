# Maintainer: Tien Thanh <tthanh.v9.16@gmail.com>

pkgname=st
pkgver=0.6.r72.g528241a
pkgrel=1
epoch=
pkgdesc="Simple virtual terminal emulator for X"
arch=('x86_64')
url="http://git.suckless.org/st"
license=('MIT')
depends=("libxft")
makedepends=("ncurses" "libxext" "git")
provides=("$pkgname")
conflicts=("$pkgname")
source=("git://git.suckless.org/st")
sha1sums=('SKIP')

pkgver() {
	cd "${srcdir}/${pkgname}"
	git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

prepare() {
	cd "${srcdir}/${pkgname}"
	cp ../../config.h .
}


build() {
	cd "${srcdir}/${pkgname}"
	make
}

package() {
	cd "${srcdir}/${pkgname}"
	sudo make install
	make clean
}

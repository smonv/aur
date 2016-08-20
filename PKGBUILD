# Maintainer: Tien Thanh <tthanh.v9.16@gmail.com>

pkgname=st-tthanh
_pkgname=st
pkgver=20160811.023225e
pkgrel=1
epoch=
pkgdesc="Simple virtual terminal emulator for X"
arch=('x86_64')
url="http://git.suckless.org/st"
license=('MIT')
depends=("libxft")
makedepends=("ncurses" "libxext" "git")
provides=("${_pkgname}")
conflicts=("${_pkgname}")
source=("git://git.suckless.org/st"
		"http://st.suckless.org/patches/st-hidecursor-20160727-308bfbf.diff")
sha1sums=('SKIP' 'SKIP')

pkgver(){
	cd "${srcdir}/${_pkgname}"
	git log -1 --format='%cd.%h' --date=short | tr -d -
}

prepare() {
	cd "${srcdir}/${_pkgname}"
	git apply ../st-hidecursor-20160727-308bfbf.diff
	git apply ../../custom.diff
}


build() {
	cd "${srcdir}/${_pkgname}"
	make config.h
	make
}

package() {
	cd "${srcdir}/${_pkgname}"
	make PREFIX="$pkgdir/usr/" DESTDIR="$pkgdir/" install
}

# Maintainer: Tien Thanh <tthanh.v9.16@gmail.com>

pkgname=st-git
pkgver=latest
pkgrel=1
epoch=
pkgdesc="Simple virtual terminal emulator for X"
arch=('x86_64')
url="http://git.suckless.org/st"
license=('MIT')
depends=("libxft")
makedepends=("ncurses" "libxext" "git")
provides=("st")
conflicts=("st")
source=("git://git.suckless.org/st"
		"http://st.suckless.org/patches/st-hidecursor-20160710-528241a.diff"
		"http://st.suckless.org/patches/st-no_bold_colors-20160710-528241a.diff")
sha1sums=('SKIP' 'SKIP' 'SKIP')

prepare() {
	cd "${srcdir}/st"
	git apply ../st-hidecursor-20160710-528241a.diff
	git apply ../st-no_bold_colors-20160710-528241a.diff
	git apply ../../base16-eighties-git-528241a.diff
}


build() {
	cd "${srcdir}/st"
	make config.h
	make
}

package() {
	cd "${srcdir}/st"
	sudo make install
	make clean
}

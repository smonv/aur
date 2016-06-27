# Maintainer: Tien Thanh <tthanh.v9.16@gmail.com>

pkgname=st
pkgver=528241a
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
source=("git://git.suckless.org/st#commit=528241a"
		"http://st.suckless.org/patches/st-hidecursor-git-20160620-528241a.diff"
		"http://st.suckless.org/patches/st-no_bold_colors-git-20160620-528241a.diff"
		"http://st.suckless.org/patches/st-solarized-dark-git-20160620-528241a.diff")
sha1sums=('SKIP' 'SKIP' 'SKIP' 'SKIP')

prepare() {
	cd "${srcdir}/${pkgname}"
	git apply ../st-hidecursor-git-20160620-528241a.diff
	git apply ../st-no_bold_colors-git-20160620-528241a.diff
	git apply ../st-solarized-dark-git-20160620-528241a.diff
	git apply ../../st-tthanh-custom-git-20160620-528241a.diff
}


build() {
	cd "${srcdir}/${pkgname}"
	make config.h
	make
}

package() {
	cd "${srcdir}/${pkgname}"
	sudo make install
	make clean
}

# Maintainer: Gaetan Bisson <bisson@archlinux.org>
# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Sebastian A. Liem <sebastian at liem dot se>

pkgname=slock-git
_pkgname=slock
pkgver=20220105.c727ae3
pkgrel=1
pkgdesc='Simple X display locker'
url='http://tools.suckless.org/slock'
arch=('i686' 'x86_64' 'armv7h')
license=('MIT')
makedepends=('git')
depends=('libxrandr')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	cd $startdir
	git log -1 --format='%cd.%h' --date=short | tr -d -
}

build() {
	cd $startdir
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd $startdir
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

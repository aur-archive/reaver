# Maintainer: Bartosz Feński <fenio@debian.org>
pkgname=reaver
pkgver=1.4
pkgrel=1
pkgdesc="brute force attack tool against an access point's WiFi Protected Setup pin number"
arch=('i686' 'x86_64')
url="http://code.google.com/p/reaver-wps/"
license=('GPL')
depends=('libpcap' 'sqlite3')
makedepends=('libpcap' 'sqlite3')
#install=$pkgname.install
source=(http://reaver-wps.googlecode.com/files/$pkgname-$pkgver.tar.gz)
md5sums=('05441dda7bacfcbe1e831c85d1ea3bc9')

build() {
	cd $srcdir/$pkgname-$pkgver/src
	./configure --prefix=/usr
	make
}

package() {
	mkdir -p $pkgdir/usr/bin $pkgdir/usr/share/doc/reaver
	install -dm755 $pkgdir/usr/bin
	install -dm755 $pkgdir/usr/share/doc/reaver
	install -dm755 $pkgdir/usr/share/man/man1
	install -m755 $srcdir/$pkgname-$pkgver/src/reaver $pkgdir/usr/bin/
	install -m755 $srcdir/$pkgname-$pkgver/src/wash $pkgdir/usr/bin/
	install -m644 $srcdir/$pkgname-$pkgver/docs/README $pkgdir/usr/share/doc/reaver/
	install -m644 $srcdir/$pkgname-$pkgver/docs/reaver.1.gz $pkgdir/usr/share/man/man1/
}

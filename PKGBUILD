# Maintainer: Remi Gacogne <rgacogne-arch at coredump dot fr>
pkgname=sslscan
pkgver=1.8.2
pkgrel=2
pkgdesc="A fast tools to scan SSL services, such as HTTPS."
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/sslscan/"
license=('GPL')
depends=('openssl')
source=(http://sourceforge.net/projects/sslscan/files/$pkgname/$pkgname-$pkgver.tgz)
md5sums=('1a890d031996ab252efb535511bd58db')
sha512sums=('89dfa5426cf9c5631fcf379931eabf020d4b084feb88bbd61e81a4b927ad19275b8613adb06a39eb4d9ce2992f4460383935f5903cfa8f0f1a2e72f8a86ec8a3')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  sed -i 's/-lssl/-lssl -lcrypto/g' Makefile
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  mkdir -p $pkgdir/usr/bin
  mkdir -p $pkgdir/usr/share/man/man1
  make BINPATH="$pkgdir/usr/bin/" MANPATH="$pkgdir/usr/share/man/" install
}

#$Id: PKGBUILD 57869 2011-11-04 01:39:34Z ebelanger $
# Maintainer: Andrea Scarpino <andrea@archlinux.org>
# Contributor: DaNiMoTh <jjdanimoth@gmail.com>

pkgname=mercury
pkgver=2.0RC8a
pkgrel=1
pkgdesc="Java Based MSN client"
arch=('any')
url="http://www.mercury.im"
license=('custom')
depends=('bash' 'java-runtime')
makedepends=('rpmextract')
source=(http://download.opensuse.org/repositories/home:/Lord_LT/openSUSE_11.4/src/Mercury-Messenger-$pkgver-2.1.src.rpm
	"license.txt")
md5sums=('b09ab56b3c63c367081932cda39653e7'
         '6ce0e815d63db6ac55a28e8d52c3f8da')

package() {
  cd "$srcdir"
  rpmextract.sh Mercury-Messenger-$pkgver-2.1.src.rpm
  tar -xf mercury-messenger-2.0rc8a.tar.bz2
  cd mercury-messenger-2.0rc8a

  install -d "$pkgdir"/usr/{bin,share/java}
  cp -r mercury "$pkgdir"/usr/share/java
  install -D -m644 desktop/mercurylogo.png "$pkgdir"/usr/share/pixmaps/mercurylogo.png
  install -D -m644 desktop/Mercury-Messenger.desktop "$pkgdir"/usr/share/applications/Mercury-Messenger.desktop
  ln -s /usr/share/java/mercury/startup/startup_linux.sh "$pkgdir"/usr/bin/mercury
  install -D -m644 "$srcdir/license.txt" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

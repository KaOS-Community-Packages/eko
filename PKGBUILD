pkgname=eko
pkgver=0.1.20160413
pkgrel=1
_commit=c3428e53eb59841f1e39094239bf1268ad534d41
pkgdesc="Qt5 sound editor"
arch=('x86_64')
url="https://github.com/psemiletov/eko"
category:AudioVideo
screenshot:http://i.imgur.com/UnNl5NE.png?1
license=('Public domain')
depends=( 'qt5-base' 'portaudio' 'libsndfile' 'libsamplerate')
makedepends=('cmake' 'qt5-tools')
source=("https://github.com/psemiletov/eko/archive/${_commit}.zip" "eko.desktop")
md5sums=('2d2c28fdc9f94f1222f13418d1c1d8a9'
         'd2d88bb1d8f3aa3dddf393459e3fed25')


build() {
  cd $pkgname-${_commit}
  qmake-qt5  PREFIX=/usr
  make
}
package() {
  cd $pkgname-${_commit}
  make INSTALL_ROOT="$pkgdir" install

  install -Dm644 $srcdir/${pkgname}.desktop $pkgdir/usr/share/applications/${pkgname}.desktop

  install -Dm644 ./icons/eko_icon.png $pkgdir/usr/share/pixmaps/eko.png
}



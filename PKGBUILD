# Maintainer:  Marcin Wieczorek <marcin@marcin.co>
# Contributor: ovi chis <ovi@ovios.org>

pkgname=libqb
pkgver=1.0.3
pkgrel=1
pkgdesc='Library with the primary purpose of providing high performance client server reusable features'
arch=('x86_64')
makedepends=('doxygen' 'splint')
depends=('glibc')
license=('LGPL2.1')
options=(!libtool)
url="https://github.com/ClusterLabs/libqb"
source=("https://github.com/ClusterLabs/$pkgname/releases/download/v$pkgver/$pkgname-$pkgver.tar.xz"
    "https://github.com/ClusterLabs/$pkgname/releases/download/v$pkgver/$pkgname-$pkgver.tar.xz.asc")
sha512sums=('9264fed8479238dadcb8d33fa5d9467d7f4dff820f361ae2e302fe1c0818ddf0bd14e069b9ec6589e466d5c7c6ed787714b081924be27c141bfc9022615cb7a8'
            'SKIP')
validpgpkeys=(
  'EA78541A2D92451106C8A1F7B67157F3A70D4537'
)

build() {
    cd "$pkgname-$pkgver"
    ./autogen.sh
    ./configure --prefix=/usr \
        --disable-fatal-warnings \
        --disable-static \
        --libdir=/usr/lib \
        --sbindir=/usr/bin
    make
}

package() {
    cd "$pkgname-$pkgver"
    make DESTDIR="${pkgdir}" install
}

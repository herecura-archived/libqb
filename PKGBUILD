# Maintainer:  Marcin Wieczorek <marcin@marcin.co>
# Contributor: ovi chis <ovi@ovios.org>

pkgname=libqb
pkgver=1.0.2
pkgrel=1
pkgdesc='Library with the primary purpose of providing high performance client server reusable features'
arch=('i686' 'x86_64')
makedepends=('doxygen' 'splint')
depends=('glibc')
license=('LGPL2.1')
options=(!libtool)
url="https://github.com/ClusterLabs/libqb"
source=("https://github.com/ClusterLabs/$pkgname/releases/download/v$pkgver/$pkgname-$pkgver.tar.xz"
    "https://github.com/ClusterLabs/$pkgname/releases/download/v$pkgver/$pkgname-$pkgver.tar.xz.asc")
sha512sums=('5f852d2abc8062ec9314b0fe163ca008a7c0780aded387a77fd7d8b0a7ff3237e0ff1f90c3e8f447a7e31604dea33d6d26901e701d5d149d932dfb8d75db7756'
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

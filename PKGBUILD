# Maintainer: Leonid Pilyugin <l.pilyugin04@gmail.com>>

pkgname=kawaii-uwufetch
pkgver=2.1
pkgrel=2
pkgdesc="A kawaii system info tool for Linux, based on nyan/uwu trend on r/linuxmasterrace."
url='https://github.com/LeonidPilyugin/kawaii-uwufetch'
arch=('x86_64')
license=('GPL3')
makedepends=("gcc")
optdepends=("viu: Display distro logos as images" "lshw: Better GPU detection")
source=(
    "uwufetch-$pkgver::https://github.com/ad-oliviero/uwufetch/archive/refs/tags/$pkgver.tar.gz"
    "kawaii-$pkgver.patch::https://github.com/LeonidPilyugin/$pkgname/releases/download/v$pkgver/kawaii.patch"
)
sha256sums=(
    '1153c826a2e332874c9ac2ee0c84ed121271445706190e444a3f585ec95d4bfc'
    '57c53fc158866cfdbe562bf906496862921e801148e7355f5c19cf1b540a3fdd'
)

prepare() {
	cd "$srcdir/uwufetch-$pkgver"
    patch -u -p1 < $srcdir/kawaii-$pkgver.patch
}

build() {
    cd "$srcdir/uwufetch-$pkgver"
    make build
}

package() {
    cd "$srcdir/uwufetch-$pkgver"
    make DESTDIR="$pkgdir/usr" ETC_DIR="$pkgdir/etc" UWUFETCH_VERSION="\"$pkgname $pkgver\"" install
    rm $pkgdir/usr/include
}


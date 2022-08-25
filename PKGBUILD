# Maintainer: Leonid Pilyugin <l.pilyugin04@gmail.com>>

pkgname=kawaii-uwufetch
pkgver=1.8
pkgrel=2
pkgdesc="A kawaii system info tool for Linux, based on nyan/uwu trend on r/linuxmasterrace."
arch=('x86_64')
url="https://github.com/TheDarkBug/uwufetch"
license=('GPL3')
makedepends=("gcc")
optdepends=("viu: Display distro logos as images" "lshw: Better GPU detection")
source=("$pkgname-$pkgver.tar.gz::https://github.com/LeonidPilyugin/$pkgname/releases/download/v$pkgver/files.tar.gz")
sha256sums=('d56c55917c643c9804917b319b170d944d709ba17d43ad7a9e5233862bb07fea')

build() {
    cd "$srcdir/files/uwufetch-$pkgver"
    make build
}

package() {
    cd "$srcdir/files/uwufetch-$pkgver"
    make DESTDIR="$pkgdir" install
}


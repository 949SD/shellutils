# Maintainer: David K david.dk949@gmail.com
_pkgname=shellutils
pkgname="${_pkgname}-949sd"
pkgver=unknown
pkgrel=2
pkgdesc="variaous shell utilities"
arch=('any')
url="https://github.com/dk949/$_pkgname"
license=('MIT')
depends=()
makedepends=()
optdepends=(
    'bat: for obat and wbat'
    'clang: for ctfix'
    'curl: for dict'
    'docker: for docker-clean-images and docker-clean-ps'
    'ffmpeg: for duration and play'
    'git: for license'
    'gnupg: for encryptdir and decryptdir'
    'grub: for update-grub'
    'poppler: for pdfcounter'
    'python: for tocgen'
    'tar: for encryptdir and decryptdir'
    'util-linux: for run (deprecated)'
    'xorg-xprop: for wminfo'
    'zstd: for getcore'
)
provides=(
    'bak'
    'cleanlatex'
    'colorcheck'
    'cpdir'
    'ctfix'
    'decryptdir'
    'dict'
    'docker-clean-images'
    'docker-clean-ps'
    'double'
    'duration'
    'encryptdir'
    'execf'
    'extrename'
    'floatdump'
    'forever'
    'fsize'
    'getcore'
    'license'
    'lstype'
    'mkfile'
    'pdfcounter'
    'obat'
    'out'
    'play'
    'rmextdup'
    'rmfile'
    'run'
    'sobrowser'
    'tocgen'
    'update-grub'
    'wbat'
    'wcat'
    'wminfo'
)
source=("$pkgname::git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make -j
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

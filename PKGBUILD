# Maintainer: David K david.dk949@gmail.com
pkgname=shellutils
pkgver=unknown
pkgrel=0
pkgdesc="Open the EDITOR. Write some code. Have it executed."
arch=('any')
url="https://github.com/dk949/$pkgname"
license=('MIT')
depends=()
makedepends=()
optdepends=()
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
source=("git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

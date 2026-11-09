# Maintainer: David K dk949.david@gmail.com
_pkgname=shellutils
pkgname="${_pkgname}-949sd"
pkgver=unknown
pkgrel=1
pkgdesc="variaous shell utilities"
arch=('any')
url="https://github.com/dk949/$_pkgname"
license=('MIT')
depends=('gcc-libs')
options=('!debug')
makedepends=('git')
optdepends=(
    'bash: for mkssh'
    'bat: for obat and wbat'
    'binutils: for obat'
    'claude-code: for ask-claude'
    'clang: for ctfix'
    'curl: for dict'
    'docker: for docker-clean-images and docker-clean-ps'
    'ffmpeg: for vid-duration and vid-play'
    'git: for license'
    'grub: for update-grub'
    'inotify-tools: for waitfor'
    'jq: for ask-claude'
    'pacman-contrib: for packageinfo'
    'poppler: for pdfcounter'
    'python: for tocgen'
    'sshfs: for mkssh'
    'systemd: for timezone'
    'xorg-xprop: for wminfo'
)
provides=(
    'ask-claude'
    'bak'
    'colorcheck'
    'ctfix'
    'dict'
    'docker-clean-images'
    'docker-clean-ps'
    'extrename'
    'floatdump'
    'fsize'
    'license'
    'line-range'
    'lstype'
    'mkfile'
    'mkssh'
    'obat'
    'out'
    'packageinfo'
    'pdfcounter'
    'rmfile'
    'timezone'
    'tocgen'
    'update-grub'
    'vid-duration'
    'vid-play'
    'waitfor'
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

# Maintainer: MR_UNKNOWN74IDK <mr.unknown74idk@proton.me>
pkgname=aptyay
pkgver=1.0.0
pkgrel=1
pkgdesc="apt-syntax wrapper for pacman, with automatic AUR helper support"
arch=('any')
url="https://github.com/MR-UNKNOWN74IDK/aptOS"
license=('AGPL3')
depends=('bash' 'pacman')
optdepends=('yay: AUR helper auto-detected and used automatically'
            'paru: AUR helper auto-detected and used automatically'
            'pacman-contrib: for the why/why-not dependency lookups')
source=("$pkgname::git+$url.git#tag=v$pkgver")
sha256sums=('SKIP')

package() {
    cd "$pkgname"
    install -Dm755 aptyay "$pkgdir/usr/bin/aptyay"
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

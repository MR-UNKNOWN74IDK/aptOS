# Maintainer: MR_UNKNOWN74IDK <mr.unknown74idk@proton.me>
pkgname=aptos
pkgver=1.0.1
pkgrel=1
pkgdesc="apt-syntax package management for pacman, with automatic AUR support"
arch=('any')
url="https://github.com/MR-UNKNOWN74IDK/aptOS"
license=('AGPL3')
depends=('bash' 'pacman')
optdepends=('yay: AUR helper auto-detected and used automatically'
            'paru: AUR helper auto-detected and used automatically'
            'pacman-contrib: for the why/why-not dependency lookups')
replaces=('aptyay')
conflicts=('aptyay')
provides=('aptyay')
source=("aptOS::git+$url.git#tag=v$pkgver")
sha256sums=('SKIP')

package() {
    cd aptOS
    install -Dm755 aptOS "$pkgdir/usr/bin/aptOS"
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

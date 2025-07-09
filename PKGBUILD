# Maintainer: MLM-stuff <gfxoxinzh@mozmail.com>

pkgname=libfprint-2-tod1-goodix
pkgver=0.0.11+2404
_debver="${pkgver}-0ubuntu1"
pkgrel=1
pkgdesc="Proprietary driver for Goodix fingerprint readers from Ubuntu launchpad"
arch=('x86_64')
url="https://launchpad.net/~libfprint-tod1-group"
license=('custom')
depends=('libfprint-tod')
makedepends=('tar')
groups=('fprint')
source=("https://launchpad.net/~libfprint-tod1-group/+archive/ubuntu/ppa/+files/${pkgname}_${_debver}_amd64.deb")
sha256sums=('SKIP')  # Update this with actual checksum

prepare() {
    cd "$srcdir"
    # Extract the deb file
    ar x "${pkgname}_${_debver}_amd64.deb"
    # Extract data archive
    tar -xf data.tar.*
}

package() {
    cd "$srcdir"
    
    # Install library files
    if [ -d "usr/lib/x86_64-linux-gnu/libfprint-2/tod-1" ]; then
        install -dm755 "$pkgdir/usr/lib/libfprint-2/tod-1/"
        install -Dm755 usr/lib/x86_64-linux-gnu/libfprint-2/tod-1/*.so "$pkgdir/usr/lib/libfprint-2/tod-1/"
    fi
    
    # Install udev rules
    if [ -d "lib/udev/rules.d" ]; then
        install -dm755 "$pkgdir/usr/lib/udev/rules.d/"
        install -Dm644 lib/udev/rules.d/*.rules "$pkgdir/usr/lib/udev/rules.d/"
    fi
    
    # Install license if present
    if [ -f "usr/share/doc/${pkgname}/copyright" ]; then
        install -Dm644 "usr/share/doc/${pkgname}/copyright" "$pkgdir/usr/share/licenses/${pkgname}/LICENSE"
    fi
}

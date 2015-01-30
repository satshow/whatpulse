
pkgname=whatpulse
pkgver=2.5
pkgrel=1
pkgdesc="Small application that measures your keyboard/mouse usage, down- & uploads and your uptime."
arch=('x86_64')
url="http://www.whatpulse.org"
license=('custom:whatpulse_tos')
install=whatpulse.install
depends=('qt' 'libpcap')
source=("http://whatpulse.org/files/whatpulse-linux-64bit-$pkgver.tar.gz")
md5sums=('6ed66006ca793db50baa5bf53ba16da1')
 
package() {
    cd $srcdir/
    mkdir -p ${pkgdir}/usr/bin
    install -m0755 whatpulse ${pkgdir}/usr/bin/
   
    mkdir -p ${pkgdir}/etc/udev/rules.d/
    cat >${pkgdir}/etc/udev/rules.d/99-whatpulse-input.rules <<__EOF__
KERNEL=="event*", NAME="input/%k", MODE="640", GROUP="input"
__EOF__
}

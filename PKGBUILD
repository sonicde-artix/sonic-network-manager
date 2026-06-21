# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=sonic-network-manager
pkgver=6.7.0
pkgrel=1
pkgdesc='SonicDE applet written in QML for managing network connections'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-network-manager'
license=(GPL-2.0-or-later)
depends=(glib2
         glibc
         kcmutils
         kcolorscheme
         kcompletion
         kconfig
         kdbusaddons
         kdeclarative
         ki18n
         kirigami-addons
         kjobwidgets
         knotifications
         kquickcharts
         kservice
         ksvg
         kwidgetsaddons
         libnm
         libstdc++
         modemmanager-qt
         networkmanager-qt
         openssl
         prison
         qcoro
         qt6-base
         qt6-declarative
         qtkeychain-qt6
         solid
         sonic-frameworks-core-addons
         sonic-frameworks-io
         sonic-frameworks-quick-ui
         sonic-frameworks-windowsystem
         sonic-interface-libraries
         sonic-workspace)
makedepends=(openconnect
             qt6-webengine
             sonic-frameworks-cmake-modules)
optdepends=('openconnect: Cisco AnyConnect VPN plugin'
            'qrca: QR code scanner'
            'qt6-webengine: Cisco AnyConnect VPN plugin')
provides=(plasma-nm)
conflicts=(plasma-nm)
groups=(sonicde)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('25ae04c4faa7f4f1a31bfa3ee0e7ce2312407352a74beab8488561dd72760ef7')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

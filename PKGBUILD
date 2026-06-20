# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=sonic-network-manager
pkgver=6.6.5
pkgrel=3
pkgdesc='SonicDE applet written in QML for managing network connections'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-network-manager'
license=(GPL-2.0-or-later)
depends=(gcc-libs
         glib2
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
         kwallet
         kwidgetsaddons
         libnm
         modemmanager-qt
         networkmanager-qt
         prison
         qca-qt6
         qcoro
         qt6-base
         qt6-declarative
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
sha256sums=('bd030602d1b9a2b189f1d1e5f6eaccebc77dd3bbe39658a75092e44458da20d5')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

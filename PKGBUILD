# Maintainer: artist for Artix Linux

pkgname=sonic-network-manager
pkgver=6.6.5
pkgrel=1
#_commit="9402eca9b8b38399e24da784a50dc03e51fd4a70"
pkgdesc='Sonic applet written in QML for managing network connections'
arch=(x86_64)
url="https://github.com/Sonic-DE/$pkgname"
license=(LGPL)
depends=(gcc-libs
         glib2
         glibc
         kcmutils
         kcolorscheme
         kcompletion
         kconfig
         sonic-frameworks-io
         kdbusaddons
         kdeclarative
         ki18n
         sonic-frameworks-io
         sonic-frameworks-quick-ui
         kirigami-addons
         kjobwidgets
         knotifications
         kquickcharts
         kservice
         ksvg
         kwallet
         kwidgetsaddons
         sonic-frameworks-windowsystem
         libnm
         sonic-interface-libraries
         modemmanager-qt
         networkmanager-qt
         sonic-workspace
         prison
         qca-qt6
         qcoro
         qt6-base
         qt6-declarative
         solid)
makedepends=(extra-cmake-modules
             openconnect
	     qt6-webengine)
optdepends=('openconnect: Cisco AnyConnect VPN plugin'
            'qrca: QR code scanner'
            'qt6-webengine: Cisco AnyConnect VPN plugin')
groups=(sonicde)
conflicts=(plasma-nm)
provides=(plasma-nm)
replaces=(plasma-nm)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/$pkgver.tar.gz")

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

sha256sums=('bd030602d1b9a2b189f1d1e5f6eaccebc77dd3bbe39658a75092e44458da20d5')


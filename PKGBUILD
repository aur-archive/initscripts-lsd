# $Id: PKGBUILD 158656 2012-05-05 14:34:35Z tomegun $
# Maintainer: Jubei-Mitsuyoshi <jubei.house.of.five.masters@gmail.com>
# Contributor: Thomas Bächler <thomas@archlinux.org>
# Contributor: Aaron Griffin <aaron@archlinux.org>
# Contributor: Ivailo Monev <xakepa10@gmail.com>

pkgname='initscripts-lsd'
_axepkgname='initscripts'
pkgver=2012.05.1
_axepkgver=2013.05.1
pkgrel=2
groups=('base' 'lsd')
arch=('any')
pkgdesc="System initialization/bootup scripts , provides initscrits 2013.05.1 so that it will never be replaced by Arch standard initscripts ,part of the -lsd innitiative"
url="http://www.archlinux.org"
license=('GPL2')
backup=('etc/inittab' 'etc/rc.conf' 'etc/rc.local' 'etc/rc.local.shutdown' 'etc/conf.d/wireless')
depends=('glibc' 'bash' 'grep' 'coreutils' 'udev>=182' 'iproute2'
         'ncurses' 'kbd' 'findutils' 'sysvinit')
provides=("initscripts=$_axepkgver")
conflicts=('initscripts')
optdepends=('bridge-utils: Network bridging support'
            'dhcpcd: DHCP network configuration'
            'net-tools: legacy network support'
            'wireless_tools: Wireless networking')
makedepends=(asciidoc)
install=initscripts.install
source=("ftp://ftp.archlinux.org/other/initscripts/${_axepkgname}-${pkgver}.tar.xz"
        'wireless.conf.d')

package() {
  cd ${srcdir}/${_axepkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
  install -D -m644 ${srcdir}/wireless.conf.d ${pkgdir}/etc/conf.d/wireless
  #axe patch, we need to get rid of this
  rm ${pkgdir}/etc/profile.d/locale.sh
  rm ${pkgdir}/usr/share/man/man5/hostname.5
  rm ${pkgdir}/usr/share/man/man5/locale.conf.5
  rm ${pkgdir}/usr/share/man/man5/vconsole.conf.5
}
md5sums=('13cff6a6638f12351892d7085d7e6fb9'
         '027576534885b8d5dded9be546057b12')
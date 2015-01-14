# Contributor: VK2ACP <anthcp@gmail.com>

pkgname=asterisk-allstar-odroid
pkgver=0.1.0.0
pkgrel=1505
pkgdesc="Asterisk with allstar mods"
arch=('armv7h')
url="http://www.asterisk.org/"
license=('GPL2')
depends=('dahdi-allstar' 'libusb' 'perl' 'svn' 'libusb-compat' 'alsa-lib')
makedepends=('linux-headers-odroid')
conflicts=('zaptel')
install="${pkgname}.install"
source=("svn+http://svn.ohnosec.org/svn/projects/allstar/astsrc-1.4.23-pre/#revision=${pkgrel}"
	"asterisk-allstar.service"
	"Makefile.trunk"
	"Makefile.gsm"
	"Makefile.libpri"
	"dahdi-channels.conf"
	"chan_dahdi.conf")
build() {
  cp "${srcdir}/Makefile.trunk" "${srcdir}/astsrc-1.4.23-pre/trunk/Makefile"
  cp "${srcdir}/Makefile.libpri" "${srcdir}/astsrc-1.4.23-pre/trunk/libpri/Makefile"
  cp "${srcdir}/Makefile.gsm" "${srcdir}/astsrc-1.4.23-pre/trunk/asterisk/codecs/gsm/Makefile"
  cd "${srcdir}/astsrc-1.4.23-pre/trunk"
  make makepkg-build
}
package() {
  cp "${srcdir}/Makefile.trunk" "${srcdir}/astsrc-1.4.23-pre/trunk/Makefile"
  cp "${srcdir}/Makefile.libpri" "${srcdir}/astsrc-1.4.23-pre/trunk/libpri/Makefile"
  cp "${srcdir}/Makefile.gsm" "${srcdir}/astsrc-1.4.23-pre/trunk/asterisk/codecs/gsm/Makefile"
  cd "${srcdir}/astsrc-1.4.23-pre/trunk"
  make DESTDIR="${pkgdir}" install_usbradio
  mkdir -p "${pkgdir}/etc/asterisk"
  cp "${srcdir}/dahdi-channels.conf" "${pkgdir}/etc/asterisk"
  cp "${srcdir}/chan_dahdi.conf" "${pkgdir}/etc/asterisk"
  mkdir -p "${pkgdir}/usr/lib/systemd/system"
  cp "${srcdir}/asterisk-allstar.service" "${pkgdir}/usr/lib/systemd/system"
}
# vim:set ts=2 sw=2 et:
md5sums=('SKIP'
         '0f7b95440d8fe3b8a48d8fa5a1568c03'
         '3fc24f4791aa366b5edaedfe82db991a'
         'c93dabeb37dfa6f566e84a1ceac639ca'
         '561982f8031886355f83e0ccef214508'
         'cfcb5fa559c08c257ed8db8a35249d6e'
         '05b73ea9cb98b1089b104c09150c5572')

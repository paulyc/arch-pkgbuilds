# Contributors:
#   Florian Pritz <f-p@gmx.at> (Original)
#   Xyne <xyne at archlinux dot us>
#   thiagoc
#   Chris <chris at christopherjones dot us>
#   henning mueller <henning@orgizm.net>
#   Fabiano Furtado <fusca14 at gmail dot com>

pkgname=fwknop
pkgver=2.6.7
pkgrel=1
pkgdesc='FireWall KNock OPerator: Single Packet Authorization and Port Knocking'
arch=(i686 x86_64)
url=https://www.cipherdyne.org/fwknop
license=(GPL)
depends=(gpgme iptables libpcap)
options=(!libtool)
backup=(
  etc/$pkgname/access.conf
  etc/$pkgname/fwknopd.conf
)
source=(
  https://www.cipherdyne.org/fwknop/download/$pkgname-$pkgver.tar.bz2
  fwknopd.service
)

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var --sbindir=/usr/bin
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
  install -D -m 755 "$srcdir/fwknopd.service" "$pkgdir/usr/lib/systemd/system/fwknopd.service"
}

sha256sums=('c25be69285956284174a3955c839767260cdcfae1ed4dd83d2319496db0563dd'
            '68bd1f59be36be5666d563f7ec561a8213c7de14ff92b77d6e38de9062331969')

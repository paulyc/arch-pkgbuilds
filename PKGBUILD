# Maintainer: grimsock <lord.grimsock at gmail dot com>
# Contributor: Alessandro Sagratini <ale_sagra at hotmail dot com>
# Contributor: Arkham <arkham at archlinux dot us>
# Contributor: LeCrayonVert < greenarrow at archlinux dot us>

pkgname=nikto
pkgver=2.1.5
pkgrel=3
pkgdesc='A web server scanner which performs comprehensive tests against web servers for multiple items'
url='http://www.cirt.net/nikto2'
license=('GPL')
arch=('any')
depends=('perl' 'openssl' 'perl-net-ssleay')
install=$pkgname.install
source=("http://www.cirt.net/nikto/$pkgname-$pkgver.tar.gz"
        "nikto.sh")

md5sums=('efcc98a918becb77471ee9a5df0a7b1e'
         'eb7b704c8bdae28af9a0353764d0b552')
sha512sums=('b6a1e7277a501055a4693d2e7179801bda0566350f3718cd169c3baf61003a936b14e9a4ba59f3597a83be8ef509953fdae546ec57e487a33b2b3efbabe84b67'
            'c4afc6ec5fa4a604e9676790fe74620162589d46eb5bc3b6d0fdd785e12f37385f4b74fd7434fb5f9f4bae05ee5c88d5d6e03f393f3c81154faf9744294bd85a')

package() {
    cd $srcdir/$pkgname-$pkgver

    install -d $pkgdir/usr/share/nikto
    cp -a * $pkgdir/usr/share/nikto/
    find $pkgdir/usr/share/nikto -type f -exec chmod 644 {} +
    install -Dm 755 $srcdir/nikto.sh $pkgdir/usr/bin/nikto
}

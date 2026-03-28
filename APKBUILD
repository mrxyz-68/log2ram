# Contributor: mrxyz-68 <mjchris68@gmail.com>
# Maintainer: mrxyz-68 <mjchris68@gmail.com>
pkgname=log2ram
pkgver=0.1
pkgrel=0
pkgdesc="log2ram for alpine linux"
url="https://github.com/mrxyz-68/log2ram"
arch="all"
license="MIT"
depends="coreutils"
makedepends="/bin/sh"
checkdepends=""
options="!check"
install="$pkgname.post-install"
#subpackages="$pkgname-dev $pkgname-doc"
source="
    "$pkgname-$pkgver".tar.gz::https://github.com/mrxyz-68/log2ram/archive/apk.tar.gz
    log2ram.initd
	log2ram.confd
    "

builddir="$srcdirr/"

package() {
    install -m755 -D "$srcdir"/$pkgname-apk/$pkgname \
        "$pkgdir"/usr/bin/$pkgname
#    install -m755 -D "$srcdir"/$pkgname-master/$pkgname-uninstall.sh \
#        "$pkgdir"/usr/bin/$pkgname-uninstall.sh
#    install -m755 -D "$srcdir"/$pkgname-master/$pkgname-cron.sh \
#        "$pkgdir"/etc/cron.d/$pkgname
    install -m644 -D "$srcdir"/$pkgname-apk/$pkgname.logrotate \
        "$pkgdir"/etc/logrotate.d/$pkgname
	install -m755 -D "$srcdir"/$pkgname.initd \
		"$pkgdir"/etc/init.d/$pkgname
	install -m644 -D "$srcdir"/$pkgname.confd \
		"$pkgdir"/etc/conf.d/$pkgname
}

sha512sums="
d1c5858ac93c7964255bf2c1a5d937d903455064dc0dbc24f089d3b4966ec5e8f902a6041cf6e6aadd7c68b6d312a982ec11770cd49d1642a9028db913c993f5  log2ram-0.1.tar.gz
68450646b30e32f5f7fef81d2c178184e08e96386e926dba9935ed6455efe495d028a98a1e92fc48c70484a4a28e41a776eb1752903cbeaa50c182d5789cb5cf  log2ram.initd
2fbcf5aa448b49ba86e2a78abc87e7dbee034250ab427d92ce78fd7cf6d36efc0d89b62a0743e085c84a941e982facd8f811fa3180a8c97904ab96bbc3fee249  log2ram.confd
"

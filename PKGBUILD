# Maintainer: Bidossessi Sodonon <bsodonon@linuxbenin.com>

pkgname=lualdap
pkgver=1.1.0
pkgrel=2
pkgdesc="A Lua interface to the OpenLDAP library"
arch=('i686' 'x86_64')
url="http://www.keplerproject.org/lualdap/"
license=('custom')
depends=('lua' 'libldap')
# http://luaforge.net/frs/?group_id=14 for latest download ID
source=(
    "http://luaforge.net/frs/download.php/2998/lualdap-1.1.0.tar.gz"
    "LICENSE"
    "lualdap-config.patch"
    "Makefile.patch"
#    "lualdap.patch"
)

build() {
    cd $srcdir/$pkgname-$pkgver
    patch -p0 < $srcdir/lualdap-config.patch
    patch -p0 < $srcdir/Makefile.patch
#    cd src
#    patch -p0 < $srcdir/lualdap.patch
#    cd ..
    make 
}
package() {
    mkdir -p "$pkgdir/usr/lib/lua/5.1"
    mkdir -p "$pkgdir/usr/share/licenses/lualdap"
  
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=${pkgdir} install
    cd $srcdir
    install -m644 "LICENSE" "$pkgdir/usr/share/licenses/lualdap/LICENSE"
}
md5sums=('5e104520c3f1333f38817a9fa1e76681'
         'e8728f500ebb96fbf5b36c66eb86f7a4'
         'c062d2fd6c691e053220bb609fb93731'
         '91ccf15a88039bf85c8409cdc1f1215f')

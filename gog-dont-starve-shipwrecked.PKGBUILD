# Maintainer: theredbaron

pkgname=gog-dont-starve-shipwrecked
pkgver=2.0.0.2
pkgrel=1
pkgdesc="Shipwrecked DLC for Don't Starve"
url="https://www.kleientertainment.com/games/dont-starve"
license=('custom')
arch=('any')
depends=('gog-dont-starve')
source=("gog://gog_don_t_starve_shipwrecked_dlc_${pkgver}.sh")
sha256sums=('d9ebb9f15bc4819730aeaad1968b4f136d2d27af0a74e80d2f3782a6c1820445')

# You need to download the gog.com installer file manually or with lgogdownloader.
DLAGENTS+=("gog::/usr/bin/echo %u - This is is not a real URL, you need to download the GOG file manually to \"$PWD\" or setup a gog:// DLAGENT. Read this PKGBUILD for more information.")

# Prevent compressing final package
PKGEXT='.pkg.tar'

prepare(){
    cd "$srcdir/data/noarch"
    [ $CARCH == "x86" ]    && rm -r "game/dontstarve64"
    [ $CARCH == "x86_64" ] && rm -r "game/dontstarve32"
}

package(){
    cd "$srcdir"
    install -d "${pkgdir}/opt/gog-dont-starve/"
    cp -r "data/noarch/game/" "${pkgdir}/opt/gog-dont-starve/"
}

# Maintainer:  Caleb Maclennan <caleb@alerque.com>
# Contributor: Asyrique Thevendran <asyrique+AUR@gmail.com>
# Contributor: Limao Luo <luolimao+AUR@gmail.com>
# Contributor: kaptoxic dragos240
# Contributor: JuanJo RuizFerrer

pkgname=rescuetime
pkgver=2.14.2.1
pkgrel=1
pkgdesc="Application time-tracking for Linux. Stable version"
arch=('i686' 'x86_64')
url=https://www.rescuetime.com
license=('GPL2')
depends=('qt4' 'xorg-xprop' 'xprintidle')
source_i686=("${pkgname}_${pkgver}_i686.deb"::"$url/installers/${pkgname}_current_i386.deb")
source_x86_64=("${pkgname}_${pkgver}_amd64.deb"::"$url/installers/${pkgname}_current_amd64.deb")
sha256sums_i686=('311b3b07b9919c2154abc8da6ac5fe87d443d2526bd26667fc18680b3089cc8c')
sha256sums_x86_64=('ca9a0d437169e43e539d044f6aad7b1acb33fde461f381774f596778320581b3')

pkgver() {
    grep Version control | cut --fields=2 -d' '
}

prepare() {
    bsdtar -xf control.tar.gz control
    bsdtar -xf data.tar.xz
}

package() {
    install -Dm644 {,"$pkgdir"/}usr/share/$pkgname/curl-ca-bundle.crt
    install -Dm755 {,"$pkgdir"/}usr/bin/$pkgname
}

post_install() {
  echo "Firefox Add-on:   https://addons.mozilla.org/en-us/firefox/addon/rescuetime-for-firefox/"
  echo "Chrome Extension: https://chrome.google.com/webstore/detail/bdakmnplckeopfghnlpocafcepegjeap"
}


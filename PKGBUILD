# Maintainer: Perberos <perberos@gmail.com"
pkgname=transformice
pkgver=1.79
pkgrel=1
pkgdesc="Transformice is a multiplayer game, where you are a small mouse out to get a cheese and bring the cheese back to the hole."
url="http://www.transformice.com/"
arch=(any)
license=('custom')
source=('http://www.transformice.com/Transformice.air'
        'transformice.sh'
        'transformice.desktop')
md5sums=('82e43f0026562e0bc072cc82e7f0ae13'
         '8b6f220985045208fa3fba923f7f12d5'
         '4c19307dd4330d74037b0e832ac1915f')
depends=(adobe-air-sdk)
makedepends=(unzip)
noextract=(Transformice.air)
install='transformice.install'

build() {
  cd "$srcdir"

  unzip -o Transformice.air || return 1
}

package() {
  cd "$srcdir"
  # air app
  install -D -m644 "${srcdir}/Transformice-chargeur-air.swf" "${pkgdir}/opt/transformice/Transformice-chargeur-air.swf"
  install -D -m644 "${srcdir}/META-INF/signatures.xml"       "${pkgdir}/opt/transformice/META-INF/signatures.xml"
  install -D -m644 "${srcdir}/META-INF/AIR/application.xml"  "${pkgdir}/opt/transformice/META-INF/AIR/application.xml"
  install -D -m644 "${srcdir}/META-INF/AIR/hash"             "${pkgdir}/opt/transformice/META-INF/AIR/hash"
  # desktop things
  install -D -m755 "${srcdir}/transformice.sh"       "${pkgdir}/usr/bin/transformice"
  install -D -m755 "${srcdir}/transformice.desktop"  "${pkgdir}/usr/share/applications/transformice.desktop"
  # icons
  install -D -m644 "${srcdir}/icone16.png"  "${pkgdir}/opt/transformice/icone16.png"
  install -D -m644 "${srcdir}/icone32.png"  "${pkgdir}/opt/transformice/icone32.png"
  install -D -m644 "${srcdir}/icone48.png"  "${pkgdir}/opt/transformice/icone48.png"
  install -D -m644 "${srcdir}/icone128.png" "${pkgdir}/opt/transformice/icone128.png"

  mkdir -p "${pkgdir}/usr/share/icons/hicolor/16x16/apps/"
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/32x32/apps/"
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/48x48/apps/"
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/128x128/apps/"

  # pixmaps links
  ln -sf "/opt/transformice/icone16.png"  "${pkgdir}/usr/share/icons/hicolor/16x16/apps/transformice.png"
  ln -sf "/opt/transformice/icone32.png"  "${pkgdir}/usr/share/icons/hicolor/32x32/apps/transformice.png"
  ln -sf "/opt/transformice/icone48.png"  "${pkgdir}/usr/share/icons/hicolor/48x48/apps/transformice.png"
  ln -sf "/opt/transformice/icone128.png" "${pkgdir}/usr/share/icons/hicolor/128x128/apps/transformice.png"
}

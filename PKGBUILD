pkgname=sublime-merge
pkgver=1.2091
pkgrel=1
pkgdesc="Git Client, done Sublime"
arch=('x86_64')
url="http://www.sublimemerge.com"
license=('custom')
depends=('libpng' 'gtk2')
install=${pkgname}.install

source=(
  "https://download.sublimetext.com/sublime_merge_build_${pkgver:2}_x64.tar.xz"
)
md5sums=('f83fa1552e96135f1c75ab341d3d17d1')

package() {
  cd "${srcdir}"

  install -dm755 "${pkgdir}/opt"
  cp --preserve=mode -r "sublime_merge" "${pkgdir}/opt/sublime_merge"

  for res in 128x128 16x16 256x256 32x32 48x48; do
    install -dm755 "${pkgdir}/usr/share/icons/hicolor/${res}/apps"
    ln -s "/opt/sublime_merge/Icon/${res}/sublime-merge.png" "${pkgdir}/usr/share/icons/hicolor/${res}/apps/sublime-merge.png"
  done

  install -dm755 "${pkgdir}/usr/share/applications"
  install -Dm644 "sublime_merge/sublime_merge.desktop" "${pkgdir}/usr/share/applications/sublime_merge.desktop"

  install -dm755 "${pkgdir}/usr/bin"
  ln -s "/opt/sublime_merge/sublime_merge" "${pkgdir}/usr/bin/sublime_merge"
}

# Maintainer: Fabian Pack <gigadoc2@revreso.de>
# Contributor: Klaas Boesche <aurkagebe@gmail.com>
# Contributor: Alexandre Isoard <alexandre.isoard@gmail.com>
pkgname=qtile-cinnamon
_pkgname=qtile
pkgver=0.1
pkgrel=2
pkgdesc="Run qtile with cinnamon-session and cinnamon-settings-daemon"
url="https://git.wdomu.link/kamil/qtile-cinnamon"
arch=('any')
license=('GPL')
depends=("qtile" "desktop-file-utils" "cinnamon-session" "cinnamon-settings-daemon" "cinnamon-control-center" "cinnamon-screensaver" "polkit-gnome")
optdepends=('cinnamon: To change cinnamon settings via UI')

install=$pkgname.install
source=(
  "$pkgname-xsession.desktop"
  "$pkgname"
  "$pkgname-app.desktop"
  "$pkgname.session"
  "cinnamon-session-$_pkgname"
)
md5sums=(
  '200c9606249ec7231a28e8f0c627a5c8'
  '398f5ac86ea455f2d1bb71a478a4d162'
  '14a004c8efa2a3589d85d89354b95d57'
  '54bb91e0bdcdedd7630c18ea98c5e3ba'
  '01a84832bc7140fd75bce6220913a16d'
)

package() {
  msg "Install $pkgname in xsessions"
  install -D -m 644 "$srcdir/$pkgname-xsession.desktop" \
    "$pkgdir/usr/share/xsessions/$pkgname.desktop"

  msg "Install $pkgname in cinnamon-session/sessions"
  install -D -m 644 "$srcdir/$pkgname.session" \
    "$pkgdir/usr/share/cinnamon-session/sessions/$pkgname.session"

  msg "Install $pkgname in /usr/share/applications"
  install -D -m 644 "$srcdir/$pkgname-app.desktop" \
    "$pkgdir/usr/share/applications/$pkgname.desktop"

  msg "Install $pkgname in /usr/bin"
  install -D -m 755 "$srcdir/$pkgname" \
    "$pkgdir/usr/bin/$pkgname"

  msg "Install cinnamon-session-$_pkgname in /usr/bin"
  install -D -m 755 "$srcdir/cinnamon-session-$_pkgname" \
    "$pkgdir/usr/bin/cinnamon-session-$_pkgname"
}

# vim:set ts=2 sw=2 et:

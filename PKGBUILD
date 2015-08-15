# Maintainer: holos

pkgname=company-mode
pkgver=0.8.12
pkgrel=1
pkgdesc='Modular in-buffer completion framework for Emacs'
arch=('any')
url="https://company-mode.github.io/"
license=('GPL')
# groups=('emacs-plugins')
depends=('emacs')
makedepends=('emacs')
source=("https://github.com/company-mode/company-mode/archive/$pkgver.tar.gz")
sha256sums=('ff7f70a13e353181526f8a11145f543955fb3f76c6772cf6d79912782a5e95ef')

prepare() {
  cd "$pkgname-$pkgver"
  rm company-yasnippet.el
}

build() {
  cd "$pkgname-$pkgver"
  make compile
}

package() {
  cd "$pkgname-$pkgver"

  install -d "$pkgdir/usr/share/emacs/site-lisp/company-mode"
  install -Dm644 company.{el,elc} company-*.{el,elc} \
    "$pkgdir/usr/share/emacs/site-lisp/company-mode"
  find "$pkgdir/usr/share/emacs/site-lisp/company-mode" \
    -name '*.el' -exec gzip {} +
}

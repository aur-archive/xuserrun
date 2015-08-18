# submitter: Gently <toddrpartridge@gmail.com>

pkgname=xuserrun
pkgver=1.1
pkgrel=1
pkgdesc="Run a program as the currently-active X.org server user"
arch=('any')
url="https://github.com/Gen2ly/xuserrun"
license=('GPL')
depends=('systemd')
makedepends=('perl')
conflicts=('xuserrun-git')
changelog=
source=("git://github.com/Gen2ly/xuserrun")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir"/$pkgname
  git describe | grep ^v | grep -o [0-9]\\.[[0-9]
}

package() {
  cd "$srcdir/$pkgname"
  install -Dm755 $pkgname    "$pkgdir/usr/bin/$pkgname"
  install -Dm644 license.txt "$pkgdir/usr/share/licenses/$pkgname/license.txt"
  install -d                 "$pkgdir/usr/share/man/man1/"
  pod2man --section=1 --center="xuserrun manual" --name="xuserrun" \
    --release="1.1" manual.pod | \
     gzip >                   "$pkgdir/usr/share/man/man1/$pkgname.1.gz"
}

# vim:set ts=2 sw=2 et:

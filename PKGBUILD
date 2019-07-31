# Maintainer: Travis LaDuke <travisladuke@gmail.com>

pkgname=lf-git
pkgver=r487.bf0dd1a
pkgrel=1
pkgdesc="Fully Decentralized Fully Replicated Key/Value Store."
arch=('x86_64')
url="https://github.com/zerotier/lf"
license=('GPL3')
depends=('gcc-libs')
makedepends=('go' 'sqlite')
# conflics=('zerotier-one')
source=("git+git://github.com/zerotier/lf.git" "lf.service")
sha512sums=('SKIP' 'SKIP')

# prepare() {
#   sed -i 's/sbin/bin/' lf.service
# }

build() {
  cd lf
  make
}

package() {
  install -Dm755 lf.service -t "$pkgdir/usr/lib/systemd/system/"
  install -Dm755 lf/lf -t "$pkgdir/usr/bin/"
}

pkgver() {
  cd lf
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

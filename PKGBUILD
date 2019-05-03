# Maintainer: zimbatm <zimbatm@zimbatm.com>
# Maintainer: ShadowKyogre <shadowkyogre.public+aur@gmail.com>
# Maintainer: rmorgans <rick.morgans@gmail.com>
pkgname=direnv
pkgver=2.20.1
pkgrel=3
pkgdesc='a shell extension that manages your environment'
arch=('x86_64' 'i686' 'armv7h')
url='https://direnv.net'
license=('MIT')
depends=('glibc')
makedepends=('go-pie')
source=("$pkgname-$pkgver.tar.gz::https://github.com/direnv/direnv/archive/v$pkgver.tar.gz")
sha256sums=('dd54393661602bb989ee880f14c41f7a7b47a153777999509127459edae52e47')

build() {
  cd "$pkgname-$pkgver"
  export GO_FLAGS="-gcflags=all=-trimpath=${PWD} -asmflags=all=-trimpath=${PWD}"
  make GO_LDFLAGS="-extldflags=${LDFLAGS}"
}

package() {
  cd "$pkgname-$pkgver"
  make install DESTDIR="$pkgdir/usr"
  install -Dm644 LICENSE.md "$pkgdir/usr/share/licenses/$pkgname/LICENSE.md"
}

# vim:set ts=2 sw=2 et:

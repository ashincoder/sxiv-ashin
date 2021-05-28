# Maintainer: Ashin Antony <ashinant15@gmail.com>

pkgname=sxiv-ashin-git
pkgver=26
pkgrel=1
pkgdesc="A 'suckless'(not a suckless utility) customized in my own way ."
arch=(x86_64)
url='https://github.com/ashincoder/sxiv-ashin.git'
license=('MIT')
depends=(libxrandr)
optdepends=()
makedepends=(git)
checkdepends=()
provides=(sxiv)
conflicts=(sxiv)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd sxiv-ashin
  printf "20170325.35633d4.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd sxiv-ashin
  make PREFIX=/usr 
}

package() {
  cd sxiv-ashin  
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}



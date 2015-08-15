# Maintainer:  jyantis <yantis@yantis.net>

pkgname=bullet-train-oh-my-zsh-theme-git
pkgver=v0.0.5.r46.g487c0b3
pkgrel=2
pkgdesc='A oh-my-zsh shell theme based on the Powerline Vim plugin'
arch=('any')
url='https://github.com/caiogondim/bullet-train-oh-my-zsh-theme'
license=('MIT')
depends=('zsh' 'oh-my-zsh-git')
source=('git+https://github.com/caiogondim/bullet-train-oh-my-zsh-theme.git')
#source=('git+https://github.com/yannrouillard/bullet-train-oh-my-zsh-theme.git')
sha256sums=('SKIP')
makedepends=('git')
provides=('bullet-train-oh-my-zsh-theme')
conflicts=('bullet-train-oh-my-zsh-theme')
install='bullet-train-oh-my-zsh-theme.install'

pkgver() {
  cd bullet-train-oh-my-zsh-theme
  set -o pipefail
  git describe --long | sed -r 's/([^-]*-g)/r\1/;s/-/./g' ||
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd bullet-train-oh-my-zsh-theme

  # We don't need anything related to git in the package
  rm -rf .git*

  # Install License which is in the readme file
  install -D -m644 README.md "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  # Install Documentation
  install -D -m644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"

  # Install the theme
  install -D -m644 bullet-train.zsh-theme "${pkgdir}/usr/share/oh-my-zsh/themes/bullet-train.zsh-theme"
}

# vim:set ts=2 sw=2 et:

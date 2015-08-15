# Maintainer: Ng Oon-Ee <ngoonee.talk@gmail.com>
# Contributor: Christoph Zeiler <archNOSPAM_at_moonblade.dot.org>

pkgname=earcandy
pkgver=0.9
pkgrel=3
pkgdesc="A sound level manager for pulseaudio that fades applications in and out based on profile and window focus"
pkgdesc="Automatic pulseaudio volume control. A sound level manager that nicely fades applications in and out based on profile and window focus."
arch=('any')
url="https://launchpad.net/earcandy"
license=('GPL')
depends=('dbus-python' 'python2-gconf' 'python2-wnck' 'python2-notify' 'pygobject' 'pulseaudio')
makedepends=('python2-distutils-extra')
source=(http://launchpad.net/$pkgname/$pkgver/$pkgver/+download/${pkgname}_$pkgver.tar.gz) 
md5sums=('8414597bb893a96f29311a17ffbc8b8d')
build() {
  cd "$srcdir/$pkgname"
 
  python2 setup.py build
}
 
package() {
  cd "$srcdir/$pkgname"
 
  python2 setup.py install --prefix "$pkgdir/usr/"
  sed -i "s|^__earcandy_data_directory__.*$|__earcandy_data_directory__ = \'/usr/share/earcandy/\'|g" ${pkgdir}/usr/lib/python2.7/site-packages/earcandy/earcandyconfig.py
}

# vim:set ts=2 sw=2 et:

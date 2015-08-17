# Contributor: Luciano A. Ferrer <laferrer@gmail.com>
pkgname=veejay-server-svn
pkgver=1221
pkgrel=1
pkgdesc="Veejay is a visual instrument and realtime video sampler for GNU/Linux, server"
arch=(i686)
url="http://www.veejayhq.net"
license="GPL"
conflicts=('veejay-server')
provides=('veejay-server')
depends=('unicap' 'libxml2' 'jack-audio-connection-kit' 'ffmpeg' 'mjpegtools')
source=()
md5sums=()

_svntrunk="svn://dyne.org/veejay/trunk/veejay-current/veejay-server"
_svnmod="veejay-server"

build() {
cd $startdir/src/

svn co $_svntrunk --config-dir ./ $_svnmod

  cp -r $startdir/src/$_svnmod $startdir/src/$_svnmod-build
  cd $startdir/src/$_svnmod-build

  ./autogen.sh
  ./configure --prefix=/usr
  make || return 1
  make DESTDIR=$startdir/pkg install

}
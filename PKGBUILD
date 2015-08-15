# Contributor: Thomas Kinnen <thomas.kinnen@gmail.com>
pkgname=fife-svn
provides="fife"
conflicts="fife"
pkgdesc="The mission of the FIFE project is to create a cross platform game creation framework"
url="http://www.fifengine.net/"
pkgver=4091
pkgrel=1
arch=('i686' 'x86_64')
license=('LGPL')
depends=('sdl' 'boost' 'sdl_ttf' 'sdl_image' 'libvorbis' 'libogg' 'openal' 'guichan' 'swig' 'python2' 'zlib' 'libgl' 'libpng' 'tinyxml')
makedepends=('scons' 'subversion')
_svntrunk="http://fife.svn.cvsdude.com/engine/trunk"
_svnmod="fife"
source=()
md5sums=()

build() {
	cd $srcdir
	if [ -d ./$_svnmod ]; then
		cd fife
		svn up
	else
		svn co $_svntrunk $_svnmod
	fi

	cd $srcdir/$_svnmod
	scons || return 1
	scons install-all --prefix $pkgdir/usr --python-prefix $pkgdir/usr/lib/python2.7/site-packages/ || return 1
}


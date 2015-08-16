# Contributor: vaca 
pkgname=myththeme-tintedglass
pkgver=20120306
pkgrel=1
pkgdesc="Themes for MythTV"
arch=('i686' 'x86_64')
url="http://http://www.thepetersclan.com/"
license=('GPL')
depends=('mythtv-git')
makedependes=('git')
provide=('mythtv')
_gitname="TintedGlass"
_gitroot="git://github.com/MythTV-Themes/TintedGlass"

build() {
  cd ${srcdir}
  msg "Connecting to GIT server...."

  if [ -d $_gitname/.git ]; then
      cd $_gitname
      git pull && git pull origin
      msg "The local files are updated."
  else
      git clone -b 0.24 "$_gitroot" "$_gitname"
      cd $_gitname
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting make..."

  rm -rf "$srcdir/$_gitname-build"

  git clone "$srcdir/$_gitname" "$srcdir/$_gitname-build"
  cd "$srcdir/$_gitname-build/"

  mkdir -p ${startdir}/pkg/usr/share/mythtv/themes/TintedGlass
  cp -r ${srcdir}/TintedGlass/* ${startdir}/pkg/usr/share/mythtv/themes/TintedGlass

}


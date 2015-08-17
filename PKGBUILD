# Maintainer: uberushaximus <uberushaximus AT gmail DOT com>

pkgname=perl-term-screen-uni
pkgver=0.04
pkgrel=1
pkgdesc='Works exactly as Term::Screen (version 1.09) on every platform Term::Screen is working plus Win32'
_dist=Term-Screen-Uni
arch=('any')
url="https://metacpan.org/release/$_dist"
license=('GPL' 'PerlArtistic')
depends=(perl perl-term-screen)
options=('!emptydirs' purge)
source=("http://cpan.metacpan.org/authors/id/T/TP/TPABA/Term-Screen/$_dist-$pkgver.tar.gz")
md5sums=('bee7eefc64c74270ad7a5c8474ea1ba6')

build() (
  cd "$srcdir/$_dist-$pkgver"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  export PERL_MM_USE_DEFAULT=1 PERL_AUTOINSTALL=--skipdeps
  /usr/bin/perl Makefile.PL
  make
)

check() (
  cd "$srcdir/$_dist-$pkgver"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  export PERL_MM_USE_DEFAULT=1
  make test
)

package() (
  cd "$srcdir/$_dist-$pkgver"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  make install INSTALLDIRS=vendor DESTDIR="$pkgdir"
)


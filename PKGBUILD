#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com> and Guillaume Horel <guillaume.horel@gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>

_langname="python"
_relname="xmldiff"

pkgname="${_langname}-${_relname}"
pkgver=2.4
pkgrel=3
pkgdesc="A libray and command line utility for diffing xml"
arch=(
  "any"
)
url="https://${_relname}.readthedocs.io"
license=(
  "BSD"
)
depends=(
  "python"
  "python-lxml"
  "python-six"
)
makedepends=(
  "python-setuptools"
)
_tarname="${_relname}-${pkgver}"
source=(
	"https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_tarname}.tar.gz"
	)
sha512sums=(
	"cc96c0d46d251ce1cf664c86f8fc0cc8fef67de6d0472415ae755e32cb86f21495dd144b5ecebba11820297a3f3cae8067c8d3b25b3107a8134b6ea641f2fc07"
	)

build() {

  cd "${_tarname}"

  python setup.py build
}

check() {

  cd "${_tarname}"

  python setup.py test
}

package() {

  cd "${_tarname}"

  python setup.py install --root="$pkgdir" --optimize=1 --skip-build

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname}/" LICENSE.txt
}

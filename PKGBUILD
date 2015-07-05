# vim:set ft=sh:
# Maintainer: graysky <graysky AT archlinux DOT us>
# Contributer: Serge Ziryukin <ftrvxmtrx@gmail.com>
# Contributor: Cyril Lashkevich <notorca at gmail dot com>

pkgname=split2flac-git
_gitname="split2flac"
pkgver=20141208.ff941ba
pkgrel=1
pkgdesc="Split flac/ape/wv/wav + cue sheet into separate tracks"
arch=('any')
url=("https://github.com/ftrvxmtrx/split2flac")
license=('MIT')
conflicts=('split2flac-hg')
depends=('cuetools' 'shntool' 'flac')
optdepends=(
	'mac:          to split APE format'
	'wavpack:      to split WV format'
	'flake:        faster FLAC encoding'
	'lame:         to split into mp3'
	'vorbis-tools: to split into ogg vorbis'
	'faac:         to split into m4a'
	'libmp4v2:     to set tags in m4a'
	'mutagen:      to set tags in mp3 with unicode support'
	'id3lib:       to set tags in mp3 unicode not supported'
	'mp3gain:      mp3 volume normalization'
	'aacgain:      m4a volume normalization'
	'vorbisgain:   ogg vorbis volume normalization'
	'imagemagick:  to convert/resize album cover images'
	'enca:         to automatically detect cue sheet charset'
)
makedepends=('git')
source=("$_gitname::git://github.com/ftrvxmtrx/split2flac.git")
sha256sums=('SKIP')

pkgver() {
	cd "$srcdir/$_gitname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

package () {
	cd ${_gitname}

	install -Dm 755 split2flac "${pkgdir}/usr/bin/split2flac"

	(
		cd "${pkgdir}/usr/bin/"
		ln -s split2flac split2mp3
		ln -s split2flac split2ogg
		ln -s split2flac split2m4a
		ln -s split2flac split2wav
	)
}

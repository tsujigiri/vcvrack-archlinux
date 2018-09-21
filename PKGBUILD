pkgname='vcvrack'
pkgver=0.6.2b
pkgrel=1
pkgdesc='Open-source virtual modular synthesizer'
url='https://vcvrack.com/'
license=(BSD)
arch=(x86_64)
depends=()
makedepends=(unzip)
source=("https://vcvrack.com/downloads/Rack-$pkgver-lin.zip")
sha256sums=(5f4a1ef666aafbf9581965d061d44119ae18b36485bada682d0de42c3a415fb3)

build() {
    unzip "Rack-$pkgver-lin.zip"
}

package() {
	mkdir -p "$pkgdir/opt"
	mv Rack "$pkgdir/opt/$pkgname"
	mkdir -p "$pkgdir/usr/bin"
	cat <<-SH > "$pkgdir/usr/bin/vcvrack"
#!/usr/bin/env sh
cd /opt/vcvrack
./Rack
SH
	chmod 755 "$pkgdir/usr/bin/vcvrack"
}


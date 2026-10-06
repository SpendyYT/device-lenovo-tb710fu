# Reference: <https://postmarketos.org/devicepkg>
maintainer=""
pkgname=device-lenovo-tb710fu
pkgdesc="Lenovo Xiaoxin Pad Pro GT"
pkgver=1
pkgrel=0
url="https://postmarketos.org"
license="MIT"
arch="aarch64"
options="!check !archcheck"
depends="
	alsa-ucm-conf	
	linux-postmarketos-qcom-sm8650
	firmware-lenovo-tb710fu-tb710fu-adreno
	firmware-lenovo-tb710fu-tb710fu-adsp
	firmware-lenovo-tb710fu-tb710fu-cdsp
	firmware-lenovo-tb710fu-tb710fu-iris
	firmware-lenovo-tb710fu-tb710fu-touchscreen
	firmware-lenovo-tb710fu-tb710fu-tplg
	firmware-lenovo-tb710fu-tb710fu-ath12k
	firmware-lenovo-tb710fu-tb710fu-qca
	firmware-lenovo-tb710fu-tb710fu-awinic
	firmware-lenovo-tb710fu-tb710fu-hexagon
	firmware-lenovo-tb710fu
	linux-firmware-qcom
	linux-firmware-qca
	linux-firmware-ath12k
	postmarketos-base
	make-dynpart-mappings
	mesa-vulkan-freedreno
	soc-qcom
	soc-qcom-qbootctl
	hexagonrpcd
	mkbootimg
	android-tools
"
makedepends="devicepkg-dev"
source="
	deviceinfo
	modules-initfs
	HiFi.conf
	Lenovo-TB710FU.conf
	LenovoTB710FU.conf
"

subpackages="
	$pkgname-openrc
"

build() {
	devicepkg_build $startdir $pkgname
}

package() {
	devicepkg_package $startdir $pkgname	

	install -Dm644 "$srcdir/HiFi.conf" \
		"$pkgdir/usr/share/alsa/ucm2/Lenovo/tb710fu/HiFi.conf"

	install -Dm644 "$srcdir/Lenovo-TB710FU.conf" \
		"$pkgdir/usr/share/alsa/ucm2/Lenovo/tb710fu/Lenovo-TB710FU.conf"

	mkdir -p "$pkgdir/usr/share/alsa/ucm2/conf.d/sm8650"
	ln -s ../../Lenovo/tb710fu/Lenovo-TB710FU.conf \
		"$pkgdir/usr/share/alsa/ucm2/conf.d/sm8650/Lenovo-TB710FU.conf"
}

openrc() {
	install_if="$pkgname=$pkgver-r$pkgrel openrc"
	install="$subpkgname.post-install"
	depends="
		qbootctl-openrc
		"
	mkdir -p "$subpkgdir"
}

sha512sums="
90127a46f50539358e5cb4f6acd57736e5c6978e8b2cb2810d30fdf8ae83cd24a6d7787fcd9171dcfead6745e1358bee1f1a7740ae410b95fcdb2e00203daddd  deviceinfo
e70bae17df23dcaaaea0e2d3616556f04baa23f8ee1357785c0f539bf97282d8ddff53953e155b72689bb73beb38c2da3d08de2a61e866684edfa10a6593885d  modules-initfs
fa06cd067ab7cef72c3874b212b1bfa277326c287321108218077bdd4a90ae4761cc5035d0268a2364ff2b2adb9e315418140668c2c6ebd160e285d40051de6a  HiFi.conf
65f394de8ccb54674500ff629e697c1d6eb75b68e556b6b5059f2b8718a45601cb53595b30ac1c0dbd76d6e630c705da09840146b4d2e48a7c4cac90c9f7d989  Lenovo-TB710FU.conf
65f394de8ccb54674500ff629e697c1d6eb75b68e556b6b5059f2b8718a45601cb53595b30ac1c0dbd76d6e630c705da09840146b4d2e48a7c4cac90c9f7d989  LenovoTB710FU.conf
"

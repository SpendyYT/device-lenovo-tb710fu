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
	linux-postmarketos-qcom-sm8650
	linux-firmware-ath12k
	linux-firmware-qca
	linux-firmware-qcom
	firmware-lenovo-tb710fu-tb710fu-adreno
	firmware-lenovo-tb710fu-tb710fu-adsp
	firmware-lenovo-tb710fu-tb710fu-cdsp
	firmware-lenovo-tb710fu-tb710fu-iris
	firmware-lenovo-tb710fu-tb710fu-touchscreen
	firmware-lenovo-tb710fu
	postmarketos-base
	make-dynpart-mappings
	mesa-vulkan-freedreno
	bootmac
	hexagonrpcd
	swclock-offset
	mkbootimg
	android-tools
"
makedepends="devicepkg-dev"
source="
	deviceinfo
	modules-initfs
"

build() {
	devicepkg_build $startdir $pkgname
}

package() {
	devicepkg_package $startdir $pkgname	
}

sha512sums="
dcbeb4eafa1b2c73a808327e97967725b07086107835326b71270e39e5d1f06e2079abb1e48b71043dc39875abbc12a545eef2192ff470c2a6bab482b6befb62  deviceinfo
e70bae17df23dcaaaea0e2d3616556f04baa23f8ee1357785c0f539bf97282d8ddff53953e155b72689bb73beb38c2da3d08de2a61e866684edfa10a6593885d  modules-initfs
"

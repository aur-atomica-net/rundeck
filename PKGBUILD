# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=rundeck
pkgver=2.4.2
pkgrel=1
pkgdesc='Open source automation service with a web console'
arch=('any')
url='http://rundeck.org/'
license=('Apache')
depends=('java-runtime')
provides=('rundeck')
conflicts=('rundeck')
replaces=('rundeck')
backup=('etc/conf.d/rundeck')
install='rundeck.install'
noextract=("rundeck-${pkgver}.jar")
source=("rundeck-${pkgver}.jar::http://download.rundeck.org/jar/rundeck-launcher-${pkgver}.jar"
        # Rename to force re-download on new version
        'rundeck.conf'
        'rundeck.service'
        'rundeck.tmpfiles.d'
        'LICENSE')
sha512sums=('8bb345e1bce572772b8ab46aeb100f1dba8f75d3c717162a78e8a823cbeecad69dd30df91b1a64b64303555560673e1229ecdd48c9320e812f29809a2be62e6e'
            'd26990839911cd9e6042e19b6305a0a862ba856c4cf9085255f8fafe99e3527a54c5ba6e910e323e9e7636e1ce5bfa1f5292ae09a103d97c90d2c7ebc8281732'
            '06855e1e77090b6a39d0777fc2bd379cc0fe01f0135bd9a5823feafc7f1913fbd19ee476f647fe637946a982d16be572faa6d242ce0ae74e48fadfa62719a3a4'
            'f61d37ace52ec23b67cb4abbd14f138dbe36288c0d48caeaf227a4629dddb7d456b4516aca06117d710a4c6bd650372de6651c9c2bba3e658027bff596b602dc'
            'd971b95f8ba0a626ff645eb8cac4fbe0590191436be1754c358b2c7f2366d084cc0b078ec5150cd8541ad93fea8a94fb579d31a9a21786c0a97732dce46ce665')

package() {
  install -Dm444 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm444 "rundeck-${pkgver}.jar" "$pkgdir/usr/share/java/rundeck/rundeck.jar"
  install -Dm644 rundeck.service "$pkgdir/usr/lib/systemd/system/rundeck.service"
  install -Dm644 rundeck.tmpfiles.d "$pkgdir/usr/lib/tmpfiles.d/rundeck.conf"
  install -Dm644 rundeck.conf "$pkgdir/etc/conf.d/rundeck"
}

# vim:set ts=2 sw=2 et:

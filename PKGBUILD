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
noextract=("rundeck-${pkgver}.war")
http://download.rundeck.org/war/rundeck-2.4.2.war
source=("rundeck-${pkgver}.war::http://mirrors.rundeck.org/war/${pkgver}/rundeck.war"
        # Rename to force re-download on new version
        'rundeck.conf'
        'rundeck.service'
        'rundeck.tmpfiles.d'
        'LICENSE')
sha512sums=('8313568bf5acb5cd4816a78ac516913d02c95a628d1eb88b1331a62e08b3083d5086991f0b0da1bd56cf61e1240b95e23833b673f3d4491666134a0183fb3bc9'
            '3a8421cef3953d899c150609f959cf5d5dd6d08d079a5e0f48bfece4f3c80491722b9e90ef841fddb87401c226b8338297c5c4e83e55a33ef8d6e387de3048d0'
            'a336b006d3711abb75b49a2e12c09ee61cf3275a2cdbbd3676480e2f6ca8ba0fb4b9c08f3f9da193252c4fca827e9a1d5eaad847d0a889445693427ae1571fe7'
            'fc82b56741c4683cde4913e41bf3dbfb0e7b16897b22b27d92a9c6fa7a300ffba97d85fbbf2287a7c5c546cb5697bbe8daa108bfc51572cf69c256d1e01e80ba'
            '0df6479a600db395c12ad29ebda3120d00460338b9a6b15913e2245aa29212a3798c32e664ca70c8034146e2e0b573066deec9e3210198202f753994e1b83efa')

package() {
  install -Dm444 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm444 "rundeck-${pkgver}.war" "$pkgdir/usr/share/java/rundeck/rundeck.war"
  install -Dm644 rundeck.service "$pkgdir/usr/lib/systemd/system/rundeck.service"
  install -Dm644 rundeck.tmpfiles.d "$pkgdir/usr/lib/tmpfiles.d/rundeck.conf"
  install -Dm644 rundeck.conf "$pkgdir/etc/conf.d/rundeck"
}

# vim:set ts=2 sw=2 et:

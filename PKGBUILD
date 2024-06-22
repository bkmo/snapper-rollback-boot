# Maintainer: Gabby <28601 dash gabby at users dot noreply dot gitlab dot freedesktop dot org>
# Maintainer: Julien <aur dot arch at fastmail dot com>
pkgname=snapper-rollback-boot
pkgver=1.0.0
pkgrel=2
pkgdesc='Script to rollback snapper snapshots as described here https://wiki.archlinux.org/index.php/Snapper#Suggested_filesystem_layout'
arch=('any')
license=('GPL3')
url='https://github.com/jrabinow/snapper-rollback'
depends=('coreutils' 'python' 'btrfs-progs')
makedepends=('git')
provides=('snapper-rollback')
conflicts=('rollback-git' 'snapper-rollback')
replaces=('rollback-git' 'snapper-rollback')
backup=(etc/snapper-rollback.conf)
install=snapper-rollback.install
source=("git+https://github.com/bkmo/snapper-rollback-boot"
        "04-snap-boot-pre-backup.hook"
        "rollback")
sha256sums=('SKIP'
            'e7bd5e8776f3c878690aa00c3d8ac9bd234de868e777fc0f3c06639a701b808e'
            '4345e07e7a04cdf6391493caf95e680f26c119a01a3aaec5fb9684b4c3790ba7')

    package() {
    install -Dm 0644  "04-snap-boot-pre-backup.hook" "$pkgdir/usr/share/libalpm/hooks/zzz-boot-backup.hook"
    install -Dm 0755  "rollback" -t "$pkgdir/usr/bin/"
    install -Dm 0644  "$pkgname/snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm 0755  "$pkgname/snapper-rollback.py" "$pkgdir/usr/bin/snapper-rollback"
}

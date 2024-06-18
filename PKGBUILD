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
        "04-snap-boot-pre-backup-hook"
        "rollback")
sha256sums=('SKIP'
            '3ad32bc61ea9df92c80581558cd32d9d4ffd8c5f231d83e6eef9873f653c8d36'
            '748676045d28fd9bcd35601754826e50cf60c70b075c1d29bb545e555347e948')

    package() {
    install -Dm 0644  "04-snap-boot-pre-backup.hook" -t "$pkgdir/usr/share/libalpm/hooks/"
    install -Dm 0755  "rollback" -t "$pkgdir/usr/bin/"
    install -Dm 0644  "$pkgname/snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm 0755  "$pkgname/snapper-rollback.py" "$pkgdir/usr/bin/snapper-rollback"
}

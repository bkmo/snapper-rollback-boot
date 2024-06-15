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
        "zz-snap-boot-post-backup.hook")
sha256sums=('SKIP'
            '299598f8ab349d7b427af854506374e8f64a08fb0d9ecda39863bd00b2af00cf'
            '7474fee3f926e2ada2720cc4cd83f4365941ab3e29d77ad0eaae265c79a7ab8d')


    package() {
    install -Dm 0644  "zz-snap-boot-post-backup.hook" -t "$pkgdir/usr/share/libalpm/hooks/"
    install -Dm 0644  "04-snap-boot-pre-backup.hook" -t "$pkgdir/usr/share/libalpm/hooks/
    install -Dm 0644  "$pkgname/snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm 0755  "$pkgname/snapper-rollback.py" "$pkgdir/usr/bin/snapper-rollback"
}

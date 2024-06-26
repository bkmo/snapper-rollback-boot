# Maintainer: Gabby <28601 dash gabby at users dot noreply dot gitlab dot freedesktop dot org>
# Maintainer: Julien <aur dot arch at fastmail dot com>
# forked from https://github.com/jrabinow/snapper-rollback with bootbackup commits

pkgname=snapper-rollback-boot
pkgver=1.0.2
pkgrel=1
pkgdesc='Script to rollback snapper snapshots as described here https://wiki.archlinux.org/index.php/Snapper#Suggested_filesystem_layout'
arch=('any')
license=('GPL3')
url='https://github.com/bkmo/snapper-rollback-boot'
depends=('coreutils' 'python' 'btrfs-progs' 'rsync')
optdepends=('snapper')
provides=('snapper-rollback')
conflicts=('rollback-git' 'snapper-rollback')
replaces=('rollback-git' 'snapper-rollback')
backup=(etc/snapper-rollback.conf)
source=("$url/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('SKIP')

    package() {
    cd $pkgname-$pkgver
    install -Dm 0644  "04-snap-boot-backup.hook" "$pkgdir/usr/share/libalpm/hooks/zz-boot-backup.hook"
    install -Dm 0755  "rollback" -t "$pkgdir/usr/bin/"
    install -Dm 0644  "snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm 0755  "snapper-rollback.py" "$pkgdir/usr/bin/snapper-rollback"
}

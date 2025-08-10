pkgname=update-notifier
pkgver=1.0
pkgrel=1
pkgdesc="Notifies you if you haven't run a full system update in X days"
arch=('any')
url=""
license=('MIT')
depends=('libnotify' 'systemd' 'pacman')
source=(
    "update-notifier.sh"
    "update-run.sh"
    "update-notifier.service"
    "update-notifier.timer"
    "update-notifier.hook"
)
sha256sums=('SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP')

package() {
    # Main scripts
    install -Dm755 "$srcdir/update-notifier.sh" "$pkgdir/usr/bin/update-notifier"
    install -Dm755 "$srcdir/update-run.sh" "$pkgdir/usr/bin/update-run"

    # Pacman hook
    install -Dm644 "$srcdir/update-notifier.hook" "$pkgdir/etc/pacman.d/hooks/update-notifier.hook"

    # Systemd user units
    install -Dm644 "$srcdir/update-notifier.service" "$pkgdir/usr/lib/systemd/user/update-notifier.service"
    install -Dm644 "$srcdir/update-notifier.timer" "$pkgdir/usr/lib/systemd/user/update-notifier.timer"
}

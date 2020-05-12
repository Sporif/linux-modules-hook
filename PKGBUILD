pkgname="linux-modules-hook"
pkgver=0.1
pkgrel=1
pkgdesc="Pacman hook for keeping your kernel modules functional after a kernel upgrade"
arch=('any')
url="https://github.com/Sporif/linux-modules-hook"
license=('MIT')
depends=('rsync')
install="${pkgname}.install"
source=("linux-modules-hook"
        "01-linux-modules-pre.hook"
        "99-linux-modules-post.hook"
        "linux-modules-cleanup.service")
sha512sums=('cc54a115848115bcd6e225c792ea065629c31689332ecd61317e1cc0ed5e00d62f6289c6ac158642f4b76663fe40336c67920775565aa36063d7edb8cad45886'
            '22dd181296672537d8a5bdbd4f4b057c87551c92af0289cc9639558a172932901b5b82c13bcc42f9be048b0e6d8a88923123d004a0c33998eb378ee008e34ce3'
            '4ee6204cc815be5466118ec2d5c9c5630be03f98b6ae018d93171c078b1a4f4d437c01603426508933b07ffab341ee12c07246708ff7a5191803867d874a1d0f'
            '30707c6589e60c4394db6a6d3ab6c511bf92c3423b9a69f004d76ec5f045bd57e6a1a142fb4d11bbb4365cb3b399cf00e445a55e45045153f6db6e1fcc8186fd')

package() {
    install -Dm755 "${srcdir}"/linux-modules-hook            -t "${pkgdir}"/usr/bin/
    install -Dm644 "${srcdir}"/*-linux-modules-*.hook        -t "${pkgdir}"/usr/share/libalpm/hooks/
    install -Dm644 "${srcdir}"/linux-modules-cleanup.service -t "${pkgdir}"/usr/lib/systemd/system/
}

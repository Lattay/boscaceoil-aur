# Maintainer: Theo Cavignac <theo.cavignac@gmail.com>

pkgname=boscaceoil-bin
pkgver=v2
pkgrel=1
pkgdesc="A free, easy to use tool for creating music! (precompiled)"
url="http://www.boscaceoil.net"
license=('BSD')
arch=('i686' 'x86_64')

depends=('adobe-air-sdk')

source=("http://www.boscaceoil.net/downloads/boscaceoil_v2_linux.tar.gz")

sha256sums=('ca30b223a348bf6bd3c5086f8dc7377eb896ed6c3bde1312cfbfb538dd247bf3')

package(){
    mkdir -p "$pkgdir"/usr/share/applications
    cat > "$pkgdir"/usr/share/applications/Boscaceoil.desktop <<EOF
[Desktop Entry]
Type=Application
Encoding=UTF-8
Name=Bosca Ceoil
GenericName=Music Editor
Comment=Easy to use tool for creating music
Icon=
Categories=Audio
Exec=boscaceoil
Terminal=false
StartupNotify=false
EOF
    mkdir -p "$pkgdir"/opt
    cp -r "$srcdir"/Boscaceoil/ "$pkgdir"/opt/Boscaceoil/

    mkdir -p "$pkgdir"/usr/bin
    cat > "$pkgdir"/usr/bin/boscaceoil <<EOF
#!/bin/sh
/opt/adobe-air-sdk/bin/adl -nodebug /opt/Boscaceoil/share/META-INF/AIR/application.xml /opt/Boscaceoil/share
EOF
    chmod 755 "$pkgdir"/usr/bin/boscaceoil
}

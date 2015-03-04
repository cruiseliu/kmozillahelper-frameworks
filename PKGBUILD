pkgname=kmozillahelper-frameworks
pkgver=0.0.1
pkgrel=1
pkgdesc="Mozilla KDE Integration, unofficial KF5 port"
arch=("i686" "x86_64")
license=('MIT')
depends=("knotifications" "kio")
provides=("kmozillahelper")
conflicts=("kmozillahelper")
makedepends=("cmake" "extra-cmake-modules")

source=("CMakeLists.txt"
        "kmozillahelper.notifyrc"
        "main.cpp"
        "main.h")

md5sums=("SKIP" "SKIP" "SKIP" "SKIP")

build() {
    mkdir -p "$srcdir/build"
    cd "$srcdir/build"

    cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release "$srcdir"
    make
}

package() {
    cd "$srcdir/build"
    make DESTDIR="$pkgdir" install
}

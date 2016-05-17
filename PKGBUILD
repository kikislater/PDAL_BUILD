# Maintainer: Sylvain POULAIN <sylvain.poulain@giscan.com>

pkgname=PDAL
pkgver=1.2
pkgrel=0
pkgdesc="PDAL is a C++ BSD library for translating and manipulating point cloud data. It is very much like the GDAL library which handles raster and vector data. See Readers and Writers for data formats PDAL supports, and see Filters for filtering operations that you can apply with PDAL."
arch=('i686' 'x86_64')
url="http://www.pdal.io/"
license=('BSD')
source=("http://download.osgeo.org/pdal/PDAL-1.2.0-src.tar.gz")
md5sums=('50ea275b74d722015358a6daae29e190')

build() {
  cd "$srcdir/$pkgname-$pkgver.$pkgrel-src"

cmake -G "Unix Makefiles" ./ \
		 -DBUILD_PLUGIN_CPD=OFF \
		 -DBUILD_PLUGIN_GREYHOUND=OFF \
		 -DBUILD_PLUGIN_HEXBIN=OFF \
		 -DBUILD_PLUGIN_ICEBRIDGE=ON \
		 -DBUILD_PLUGIN_MRSID=OFF \
		 -DBUILD_PLUGIN_NITF=OFF \
		 -DBUILD_PLUGIN_OCI=OFF \
		 -DBUILD_PLUGIN_P2G=OFF \
		 -DBUILD_PLUGIN_PCL=ON \
		 -DBUILD_PLUGIN_PGPOINTCLOUD=ON \
		 -DBUILD_PLUGIN_SQLITE=ON \
		 -DBUILD_PLUGIN_RIVLIB=OFF \
		 -DBUILD_PLUGIN_PYTHON=ON \
		 -DCMAKE_INSTALL_PREFIX=/usr \
		 -DENABLE_CTEST=OFF \
		 -DWITH_APPS=ON \
		 -DWITH_LAZPERF=OFF \
		 -DWITH_GEOTIFF=ON \
		 -DWITH_LASZIP=ON \
		 -DWITH_TESTS=ON \
		 -DCMAKE_BUILD_TYPE=Release .

make -j8
}

package() {
  cd "$srcdir/$pkgname-$pkgver.$pkgrel-src"
  make DESTDIR="$pkgdir" install
}

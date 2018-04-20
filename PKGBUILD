# Script generated with Bloom
pkgdesc="ROS - This package contains the source code for testing and comparing trac_ik"


pkgname='ros-lunar-trac-ik-examples'
pkgver='1.4.11_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'ros-lunar-catkin'
'ros-lunar-orocos-kdl'
'ros-lunar-trac-ik-lib'
)

depends=('boost'
'ros-lunar-orocos-kdl'
'ros-lunar-pr2-description'
'ros-lunar-trac-ik-lib'
'ros-lunar-xacro'
)

conflicts=()
replaces=()

_dir=trac_ik_examples
source=()
md5sums=()

prepare() {
    cp -R $startdir/trac_ik_examples $srcdir/trac_ik_examples
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}


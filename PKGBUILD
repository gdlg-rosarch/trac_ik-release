# Script generated with Bloom
pkgdesc="ROS - The trac_ik_python package contains a python wrapper using SWIG for trac_ik_lib"


pkgname='ros-lunar-trac-ik-python'
pkgver='1.4.11_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-rospy'
'ros-lunar-tf-conversions'
'ros-lunar-trac-ik-lib'
'swig'
)

depends=('ros-lunar-rospy'
'ros-lunar-tf'
'ros-lunar-tf-conversions'
'ros-lunar-trac-ik-lib'
'swig'
)

conflicts=()
replaces=()

_dir=trac_ik_python
source=()
md5sums=()

prepare() {
    cp -R $startdir/trac_ik_python $srcdir/trac_ik_python
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


# Script generated with Bloom
pkgdesc="ROS - The urdf_sim_tutorial package"


pkgname='ros-kinetic-urdf-sim-tutorial'
pkgver='0.3.0_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-controller-manager'
'ros-kinetic-diff-drive-controller'
'ros-kinetic-gazebo-ros'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-joint-state-controller'
'ros-kinetic-position-controllers'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-rqt-robot-steering'
'ros-kinetic-rviz'
'ros-kinetic-urdf-tutorial'
'ros-kinetic-xacro'
)

conflicts=()
replaces=()

_dir=urdf_sim_tutorial
source=()
md5sums=()

prepare() {
    cp -R $startdir/urdf_sim_tutorial $srcdir/urdf_sim_tutorial
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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


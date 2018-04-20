# Script generated with Bloom
pkgdesc="ROS - Python interface for camera calibration information. This ROS package provides a CameraInfo interface for Python camera drivers similar to the C++ camera_info_manager package."
url='http://ros.org/wiki/camera_info_manager_py'

pkgname='ros-kinetic-camera-info-manager-py'
pkgver='0.2.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-rosunit'
'ros-kinetic-sensor-msgs'
)

depends=('python2-rospkg'
'python2-yaml'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=camera_info_manager_py
source=()
md5sums=()

prepare() {
    cp -R $startdir/camera_info_manager_py $srcdir/camera_info_manager_py
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


# Script generated with Bloom
pkgdesc="ROS - An automatically generated package with all the configuration and launch files for using the Pepper robot with the MoveIt Motion Planning Framework"


pkgname='ros-kinetic-pepper-moveit-config'
pkgver='0.0.8_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-joint-state-publisher'
'ros-kinetic-moveit-fake-controller-manager'
'ros-kinetic-moveit-planners-ompl'
'ros-kinetic-moveit-ros-move-group'
'ros-kinetic-moveit-simple-controller-manager'
'ros-kinetic-pepper-description'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-xacro'
)

conflicts=()
replaces=()

_dir=pepper_moveit_config
source=()
md5sums=()

prepare() {
    cp -R $startdir/pepper_moveit_config $srcdir/pepper_moveit_config
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


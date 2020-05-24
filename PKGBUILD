# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - visualization_msgs is a set of messages used by higher level packages, such as rviz, that deal in visualization-specific data."
url='https://wiki.ros.org/visualization_msgs'

pkgname='ros-noetic-visualization-msgs'
pkgver='1.12.7'
arch=('any')
pkgrel=1
license=('BSD')

ros_makedepends=(
	ros-noetic-message-generation
	ros-noetic-std-msgs
	ros-noetic-catkin
	ros-noetic-geometry-msgs
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
	ros-noetic-message-runtime
	ros-noetic-std-msgs
	ros-noetic-geometry-msgs
)

depends=(
	${ros_depends[@]}
)

_dir="common_msgs-${pkgver}/visualization_msgs"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/common_msgs/archive/${pkgver}.tar.gz")
sha256sums=('a9d8c7655d426afe8bc2b021e0bc8ce25dae70ca35b985a0ec0b8b5768722bd4')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}

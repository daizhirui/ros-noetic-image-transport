# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - image_transport should always be used to subscribe to and publish images."
url='https://wiki.ros.org/image_transport'

pkgname='ros-noetic-image-transport'
pkgver='1.12.0'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=2
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
	ros-noetic-rosconsole
	ros-noetic-roscpp
	ros-noetic-message-filters
	ros-noetic-sensor-msgs
	ros-noetic-pluginlib
	ros-noetic-roslib
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
	ros-noetic-rosconsole
	ros-noetic-roscpp
	ros-noetic-message-filters
	ros-noetic-sensor-msgs
	ros-noetic-pluginlib
	ros-noetic-roslib
)

depends=(
	${ros_depends[@]}
)

_commit="21aac6a4b84017c10e8ed7ad86bc59826a77aa1f"
_dir="image_common-${_commit}/image_transport"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-perception/image_common/archive/${_commit}.tar.gz")
sha256sums=('b367ef2bac0222a747c5dac760055a80b3569b408021522afe61c15e19e2c246')

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

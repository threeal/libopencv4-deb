cmake_minimum_required(VERSION 3.10)

add_subdirectory("opencv")

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_NAME "libopencv4-dev")
set(CPACK_DEBIAN_FILE_NAME DEB-DEFAULT)
set(CPACK_DEBIAN_PACKAGE_VERSION 4.3.0)
set(CPACK_DEBIAN_PACKAGE_RELEASE 3)
set(CPACK_DEBIAN_PACKAGE_DEPENDS
  "pkg-config, libc6 (>= 2.27), libjpeg-dev, libtiff-dev, libopenjp2-7-dev, libavcodec-dev, libavformat-dev, libswscale-dev, libavresample-dev, libgstreamer1.0-dev, libgstreamer-plugins-base1.0-dev, libdc1394-22-dev"
)
set(CPACK_DEBIAN_PACKAGE_CONFLICTS "libopencv-dev")
set(CPACK_DEBIAN_PACKAGE_REPLACES "libopencv-dev")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "Alfi Maulana <alfi.maulana.f@gmail.com>")
set(CPACK_DEBIAN_PACKAGE_DESCRIPTION
  "development files for OpenCV 4
 The Open Computer Vision Library is a collection of algorithms and sample
 code for various computer vision problems. OpenCV provides low level portable
 data types and operators, and a set of high level functionalities for vide
 acquisition, image processing and analysis, structural analysis and object
 tracking, object recognition, camera calibration and 3D reconstruction."
)
set(CPACK_DEBIAN_PACKAGE_HOMEPAGE "https://github.com/opencv/opencv")

include(CPack)
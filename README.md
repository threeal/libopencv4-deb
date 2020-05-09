# Lib OpenCV 4 Deb

This repository contains CMake with CPack build project for the OpenCV 4 library.
It was created to accomodate the library packaging using the debian packaging system.

## Usage

### Updating the Source Code

- Initialize and update the `opencv` submodule.
  ```bash
  $ git submodule init
  $ git submodule update
  ```
- Move to the `opencv` directory, pull the latest update, and checkout to the latest release tag.
  ```bash
  $ cd opencv
  $ git pull
  $ git checkout <latest-release>
- Change some variables value as follow:
  - Change the value of `CPACK_DEBIAN_PACKAGE_VERSION` variable to match with the source code
      release version.
  - Increase the value of `CPACK_DEBIAN_PACKAGE_RELEASE` variable if there is changes related to
      the debian packaging with the same source code release version. else reset it to `1`.

### Building the Library

- Create a `build` directory and move to it.
  ```bash
  $ mkdir build
  $ cd build
  ```
- Configure the Makefile rules  with `/usr` as the install prefix.
  ```bash
  $ cmake -DCMAKE_INSTALL_PREFIX=/usr ..
  ```
- Build the library.
  ```bash
  $ make
  ```
  > Note: you could speed up the build process with specifying the job count parameter using `-jn` where `n` is number of the jobs. _(example: `$ make -j4`)_
- Create debian package using cpack.
  ```bash
  $ cpack
  ```
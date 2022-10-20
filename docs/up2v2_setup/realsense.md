# Intel Realsense Setup

No official support for kernel 5.15 is available from Intel Realsense.

A workaround is to use a community contribuition.

Unplug your realsense camera.

To install just:

`wget https://github.com/mengyui/librealsense2-dkms/releases/download/initial-support-for-kernel-5.15/librealsense2-dkms-dkms_1.3.14_amd64.deb`

Then:

`sudo dpkg -i librealsense2-dkms-dkms_1.3.14_amd64.deb`

`rm librealsense2-dkms-dkms_1.3.14_amd64.deb`

Now your kernel is patched with realsense.

Verify that the kernel is updated :
`modinfo uvcvideo | grep "version:"` should include `realsense` string.

Proceed installing all other realsense packages.

`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE || sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE`

`sudo add-apt-repository "deb https://librealsense.intel.com/Debian/apt-repo $(lsb_release -cs) main" -u`

`sudo apt-get install librealsense2-utils`

`sudo apt-get install librealsense2-dev`

`sudo apt-get install librealsense2-dbg`

Attach you realsense camera.

Run `realsense-viewer` to play with your camera and test it.










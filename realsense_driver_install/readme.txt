reference::
https://lifuguan.github.io/d435i/ros/2019/05/28/realsense-melodic-installation/

1. download source
git clone https://github.com/IntelRealSense/librealsense
cd librealsense

2.install dependency
apt-get install libudev-dev pkg-config libgtk-3-dev
apt-get install libusb-1.0-0-dev pkg-config
apt-get install libglfw3-dev
apt-get install libssl-dev

3.install Intel Realsense permission scripts located in librealsense source directory
sudo cp config/99-realsense-libusb.rules /etc/udev/rules.d/
sudo udevadm control --reload-rules && udevadm trigger 

4.
mkdir build
cd build
cmake ../ -DBUILD_EXAMPLES=true -DCMAKE_BUILD_TYPE=Release
make
sudo make install

5.try 
./rs-capture 

6.install ros
reference:: 
https://github.com/ros/rosdistro/pull/20651
https://github.com/IntelRealSense/realsense-ros/pull/665

6.1 https://github.com/IntelRealSense/realsense-ros.git
6.2 https://github.com/pal-robotics/ddynamic_reconfigure
6.3 catkin_make

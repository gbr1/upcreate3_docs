# Setup ROS2 UP Create® 3 packages

### 1. Intel Realsense

First at all you need to install [realsense_ros](https://github.com/IntelRealSense/realsense-ros)
```bash
cd ~/dev_ws/src
git clone -b ros2-development https://github.com/IntelRealSense/realsense-ros
cd ..
rosdep install -i --from-path src --rosdistro $ROS_DISTRO --skip-keys=librealsense2 -y

colcon build --symlink-install
source install/setup.bash
```

Now Realsense works on ROS2.

Learn more at: [https://github.com/IntelRealSense/realsense-ros](https://github.com/IntelRealSense/realsense-ros)

### 2. Packages

Clone the repos:
```bash
cd ~/dev_ws/src
git clone -b galactic https://github.com/gbr1/upcreate
git clone -b galactic https://github.com/gbr1/upcreate_robot
git clone -b galactic https://github.com/gbr1/upcreate_simulator
```

install dependencies and build:
```bash
cd ..
rosdep install -i --from-path src --ignore-src -r -y
colcon build --symlink-install
source install/setup.bash
```

Your robot is ready!

<br>
<br>
<br>



>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License



```bash
cd ~/dev_ws/src
git clone -b ros2-development https://github.com/IntelRealSense/realsense-ros
cd ..
rosdep install -i --from-path src --rosdistro $ROS_DISTRO --skip-keys=librealsense2 -y

colcon build --symlink-install
source install/setup.bash
```

Now Realsense works on ROS2

Learn more at: [https://github.com/IntelRealSense/realsense-ros](https://github.com/IntelRealSense/realsense-ros)

>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License



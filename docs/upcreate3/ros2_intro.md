# ROS2 on UP Create® 3

The following scheme introduce you the ROS2 robot architecture.

![ros2_architecture](../schemes/ros2_architecture.drawio.png)

The SLAM is compute by [rtabmap](http://introlab.github.io/rtabmap/).

It is possible to monitor your robot via [rosboard](../utilities/rosboard.md) and [foxglove](../utilities/foxglove.md) studio. You can just use a [joypad](../utilities/joypad.md) to control it.

<br>

UP Create® 3 is based on different ROS2 packages:
- [upcreate3](https://github.com/gbr1/upcreate3):
    - upcreate3_description, urdf of the robot
- [upcreate3_robot](https://github.com/gbr1/upcreate3_robot).
    - upcreate3_bringup, launch all the nodes of the robot
    - upcreate3_navigation, slam and navigation stack
    - upcreate3_robot, robot package
- [upcreate3_simulator](https://github.com/gbr1/upcreate3_simulator).
    - upcreate3_gazebo, gazebo simulation


Go to "[setup ros2 on your robot](./prepare_ros2_environment.md)" to start working on the UP Create® 3.





>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License
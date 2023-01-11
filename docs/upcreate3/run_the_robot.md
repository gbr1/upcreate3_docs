# Let's play with UP Create® 3

Now you are robot is ready to run!

To start your robot, you need to launch the bringup:
```bash
ros2 launch upcreate3_bringup bringup.launch.py
```

<br>
<br>

An rviz file is located in upcreate3_navigation package.

It can be useful to take a look at 3d maps, costmaps and play with nav2.

If you set a 2d pose in rviz the robot will reach it.

![nav2_rviz](/docs/images/nav2_rviz.png)



---
*KNOW ISSUES:*
- sometimes ***nav2*** crashes, so restart
- sometimes the ***rtabmap*** crashes, so restart
- you can't watch iRobot Create® 3 topics if the robot isn't connected to the WiFi (e.g. /odom can't be looked up across the network)


>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License
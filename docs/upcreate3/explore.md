# Autonomous exploration with UP Create® 3

***NOTE:*** this is a WIP page

The autonomous exploration relies on explore_lite in the m-explore package.

To install it just:
```bash
cd ~/dev_ws/src
git clone https://github.com/robo-friends/m-explore-ros2
cd ..
rosdep install -i --from-path src --ignore-src -r -y
colcon build --symlink-install
source install/setup.bash
```

A parameters file is present in upcreate3_navigation package and it is ready to use.

To run autonomous exploration just run the following command after the bringup:

```bash
ros2 run explore_lite explore --ros-args --params-file <full-path-to-workspace>/dev_ws/src/upcreate3_robot/upcreate3_navigation/config/explore.yaml
```

The robot will start an environment exploration. When full discovered will be back to the starting point.

---
*KNOW ISSUES:*
- /global_coastmap/costmap topic is used instead /rtabmap/map because rtabmap not publish /rtabmap/map_updates


>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License
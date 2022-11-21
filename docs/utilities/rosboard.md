# rosboard

Rosboard is a very useful web interface for your ROS based robot!

Install prerequisites:

```bash
sudo apt install python3-pip
sudo pip3 install tornado
sudo pip3 install simplejpeg
```
Then clone the repo and build it!
```bash
cd ~/dev_ws/src
git clone https://github.com/dheera/rosboard

cd ..
colcon build --symlink-install
source install/setup.bash
```

To run
```bash
ros2 run rosboard rosboard_node
```
open your favourite web browser and go to `<your robot ip>:8888`

<br>

Learn more at: [rosboard](https://github.com/dheera/rosboard)

>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License

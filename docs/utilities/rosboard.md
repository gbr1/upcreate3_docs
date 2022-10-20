# rosboard

```bash
sudo apt install python3-pip
sudo pip3 install tornado
sudo pip3 install simplejpeg

cd ~/dev_ws/src
git clone https://github.com/dheera/rosboard

cd ..
colcon build --symlink-install
source install/setup.bash
```

to run

```bash
ros2 run rosboard rosboard_node
```
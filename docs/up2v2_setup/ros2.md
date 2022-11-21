# ROS2 Galactic installation and setup

In this section you will be guided into ROS2 installation and setup.

## Install ROS2 Galactic
```bash
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```

```bash
sudo apt update && sudo apt install curl gnupg lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

```bash
sudo apt update
sudo apt upgrade
sudo apt install ros-galactic-desktop
```

```bash
echo "source /opt/ros/galactic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## Setup Fast DDS
```bash
echo "export RMW_IMPLEMENTATION=rmw_fastrtps_cpp" >> ~/.bashrc
source ~/.bashrc
```

## Setup workspace and tools

Install colcon

```bash
sudo apt install python3-colcon-common-extensions
```


Create a workspace

```bash
mkdir -p ~/dev_ws/src
cd ~/dev_ws
```

Setup rosdep

```bash
sudo apt install python3-rosdep2
rosdep update
rosdep install -i --from-path src --rosdistro galactic -y
```

```bash
colcon build --symlink-install

echo "source ~/dev_ws/install/setup.bash " >> ~/.bashrc
```


>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License

# UP Squared v2 initial setup

### Install Ubuntu 20.04

You need to install Ubuntu 20.04 with 5.15 kernel.

Flash an USB pen drive with the iso (e.g. using Balena Etcher) and put in your UP Squared v2.

Connect a monitor, keyboard and a mouse and turn on your UP Squared v2. If it already mounted in your iRobot Create® 3, just turn on your Create® robot.

During the installation process, disable your ethernet connection if you have already connected the Up to the Create.

Connect to the WiFi, choose minimal setup and install updates and third parts software and drivers.

After getting the installation done, remove the USB pen drive and press enter reboot.

Now you need to install other software.

It can be useful to use ssh on your robot, so:

```bash
sudo apt install openssh-server
```

and also git:

```bash
sudo apt install git
```


### Install UP patches

This patch allows to use GPIOs and other peripherihals on UP Squared v2.

Let's start installing dkms:

```bash
sudo apt install dkms
sudo reboot
```

Now install the patch:

```bash
wget https://github.com/up-division/pinctrl-upboard/releases/download/rc1/pinctrl-upboard_0.5.0_all.deb
sudo dpkg -i pinctrl-upboard_0.5.0_all.deb
rm pinctrl-upboard_0.5.0_all.deb
sudo reboot
```


### Configure ethernet network to connect UP2v2 to iRobot Create® 3

In this part, you will be guided to configure the ethernet connection between UP Squared v2 and iRobot Create® 3.

The first thing, you have 2 ethernet ports on UP Squared.

The one near the heatsink is called `enp1s0` the other one is `enp2s0`. It is suggested to use `enp1s0` because the cable management is easier.

To configure you need to edit the network manager file as above:
```bash
sudo nano /etc/netplan/01-network-manager-all.yaml
```

You should have something similar to:

```yaml
network:
 version: 2
 renderer: NetworkManager
 ethernets:
  enp1s0:
   dhcp4: no
   addresses:
   - 192.168.186.3/24
   gateway4: 192.168.186.1
```

***NOTE: iRobot Create® 3 ip is `192.168.186.2`, so `192.168.186.3` is the ip assigned to UP Squared v2.***

Test the connection, apply and check ip:

```bash
sudo netplan try
sudo netplan apply
ip a
sudo poweroff
```

Now the UP is tunerd off. You need to turn off also the Create robot.

Remove the robot from the dock, press the center button to turn off. You will listen the shutdown sound.

Turn on the robot placing again on the docking station and your connection will be active.


### Synchronize UP Squared v2 and iRobot Create® 3

Install chrony:
```bash
sudo apt install chrony
```

Then edit the following file:
```bash
sudo nano /etc/chrony/chrony.conf
```

Add the following lines after the `pool #.ubuntu.pool.ntp.org iburst maxsources #` block


```yaml
server 192.168.186.2 presend 0 minpoll 0 maxpoll 0 iburst  prefer trust
# Enable serving time to ntp clients on 192.168.186.0 subnet.
allow 192.168.186.0/24
```
Save the file, then:

```bash
sudo service chrony restart
```

Check if everything is ok by:
```bash
sudo chronyc clients
```

If `192.168.186.2` doesn't appear, turn off UP2V2:

```bash
sudo poweroff
```

Then remove the robot from the dock and turn it off. After that reattach the robot to the dock to turn it on again.

Check again with `chronyc clients`

Learn more about this section at: [https://iroboteducation.github.io/create3_docs/setup/compute-ntp/](https://iroboteducation.github.io/create3_docs/setup/compute-ntp/)


>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License

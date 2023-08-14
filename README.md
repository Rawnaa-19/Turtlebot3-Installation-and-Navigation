# Turtlebot3 Installation and Navigation
## Table of Contents : 
1. [Turtlebot](#Turtlebot)
    - [Commands](#Turtlebot-Commands)
    - [Launching](#Turtlebot-Launching)
1. [Rviz](#Rviz)
    - [Launching Commands](#Rviz-Commands)
    - [Navigation](#Rviz-Navigation)
    - [Save the Map](#Save-the-Map)
## Turtlebot
### Turtlebot Commands
Used the following commands to install turtlebot on ROS Melodic.
```
$  mkdir turtlebot3
$ cd ~/turtlebot3/
$ mkdir src
$ catkin_init_workspace src
$ cd src
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_autorace.git
$ cd ..
$ sudo apt-get install ros-melodic-slam-karto
$ catkin_make
$ source ~/catkin_ws/devel/setup.bash
$ rospack profile
$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
$ source ~/.bashrc
```
### Turtlebot Launching
```
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
<br><br>
<kbd> **Figure 1** <br><br>*Turtlebot Installed*<br><br> <kbd>![image](https://github.com/Rawnaa-19/Turtlebot3-Installation-and-Navigation/assets/106926557/aa9f8121-212e-424c-88de-ac84d97053ca)</kbd></kbd>

## Rivz
### Rviz Commands
First I changed the URL in ~/.ignition/fuel/config.yaml from "url: https://api.ignitionfuel.org" --> "url: https://api.ignitionrobotics.org"
```
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=karto
```
<br><br>
<kbd> **Figure 2** <br><br>*Turtlebot Installed*<br><br> <kbd>![image](https://github.com/Rawnaa-19/Turtlebot3-Installation-and-Navigation/assets/106926557/156c39c5-67cd-4a3b-946f-4649d4806c87)</kbd></kbd>
### Rviz Navigation
Used the following command to navigate using keyboard letters.
```
$ rosrun turtlebot3_teleop turtlebot3_teleop_key
```
<br><br>
<kbd> **Figure 3** <br><br>*Navigate Using Keyboard*<br><br> <kbd>![image](https://github.com/Rawnaa-19/Turtlebot3-Installation-and-Navigation/assets/106926557/1e0dc253-1002-4595-abc8-7ebb75b20d37)</kbd></kbd>
### Save the Map
Command Used to save the map."attached under the name map.pgm"
```
$ rosrun map_server map_saver -f ~/map
```
<kbd> **Figure 4** <br><br>*Map After Navigation*<br><br> <kbd>![image](https://github.com/Rawnaa-19/Turtlebot3-Installation-and-Navigation/assets/106926557/680f3a60-23b2-4bc5-a8b1-6e9bf3056ab9)</kbd></kbd>

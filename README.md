# Udacity Robotics Nanodegree
# Project #2: Go Chase It
![Go Chase It Demo](demo.gif)

## Introduction
This project involves designing and building a mobile robot that is capable of chasing and following white colored balls.

## Structure
There are two packages within this repository:

### 1. my_robot
This package defines the mobile robot under URDF as well the world that it is housed within.

### 2. ball_chaser
This package contains two nodes:

#### a) process_image
This node receives an image from the mobile robot's camera and locates the position of the white ball in its fielf of view.

#### b) drive_bot
This node receives the location data from the process_image node and then drives the robot appropriately by controlling its linear x and angular z velocities.

## Setup
First, install Gazebo and ROS on Linux.

Then, create a catkin workspace with a src/ directory and initialize the workspace:
'''console
$ mkdir -p catkin_ws/src
$ cd catkin_ws/src
$ catkin_init_workspace
'''

Next, download the packages within this repository called 'my_robot' and 'ball_chaser':
'''
$ git clone https://github.com/grejj/RoboticsND-Go-Chase-It.git
$ cp -R RoboticsND-Go-Chase-It/ball_chaser
$ cp -R RoboticsND-Go-Chase-It/my_robot
$ rm -rf RoboticsND-Go-Chase-It
'''

Then, build the packages:
'''
$ cd ..
$ catkin_make
'''

To open gazebo with the robot in it:
'''
$ source devel/setup.bash
$ roslaunch my_robot world.launch
'''

Finally, start the ball_chaser nodes in another terminal so that the robot can start following the white ball:
'''
$ source devel/setup.bash
$ roslaunch ball_chaser ball_chaser.launch

Now, when the white ball is moved within view of the front-facing camera on the robot, the robot will begin the chase the white ball.

# TurtleBot3-SLAM-Simulation
SLAM (Gmapping) simulation using TurtleBot3 robot

TurtleBot3 is a 2 wheel robot that operates similar to how a Roomba vacuum cleaner does. The simulation will be ran in Gazebo for the virtual enviroment and RVIZ paired with SLAM (Simultaneous Localization and Mapping) will display the mapping process the bot goes through

* Ubuntu 20.04.4

* ROS NOETIC

## Installing TurtleBot3
Open the terminal (CMD commands)
```
1 - sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers

2 - sudo apt install ros-noetic-dynamixel-sdk

3 - sudo apt install ros-noetic-turtlebot3-msgs

4 - sudo apt install ros-noetic-turtlebot3

5 - cd ~/catkin_*workspace name*/src/

6 - git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

7 - cd ~/catkin_*workspace name*

8 - catkin_make
```

## Simulation
As stated above we'll be using gazebo to run a virtual enviroment. You can create your own enviroment, but for simplicity sake we'll use a pre-existing one

1. Open a new terminal and input the following commands

```
  1 - source /home/*username*/catkin_*workspace name*/devel/setup.bash
  2 - export TURTLEBOT3_MODEL=burger
  3 - roslaunch turtlebot3_gazebo turtlebot3_house.launch
```
Replace the *username* and *workspace name* tags accordingly



2. Open another terminal amd input the following commands
```
1 - source /home/*username*/catkin_*workspace name*/devel/setup.bash
2 - export TURTLEBOT3_MODEL=burger
3 - roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
Replace the *username* and *workspace name* tags accordingly


3. Open another terminal amd input the following commands
```
1 - source /home/*username*/catkin_*workspace name*/devel/setup.bash
2 - export TURTLEBOT3_MODEL=burger
3 - roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
Replace the *username* and *workspace name* tags accordingly


4. Open Rviz and Gazebo side by side and have the 3rd terminal overlap them

5. You can now control the robot through the 3rd terminal using the w a s d x and being the mapping process

![11](https://user-images.githubusercontent.com/90250848/187880119-74550fce-f7ab-4b3c-808e-12be0870a4e8.png)

![184439348-31010fb3-44cd-4cc8-a298-0553551c4d5b](https://user-images.githubusercontent.com/90250848/187880212-17140b29-70a6-423e-bb88-0f96efe58797.png)

![184441862-a0504456-ab6e-4a7c-97ee-98e6a9897134](https://user-images.githubusercontent.com/90250848/187880284-3dbc0289-21a2-4ebe-b5cc-0cb2e381decd.png)


6. After you cover the entire building, the map should look something like this

![184446143-4ae800f7-21ad-4517-81d5-0420e52b1610](https://user-images.githubusercontent.com/90250848/187880320-5415fce3-0362-47c3-b924-06f259c11680.png)


7. Finally save the map by opening a new terminal and inputting the following command

```
rosrun map_server map_saver -f ~/map
```
![184446788-9f542b79-fe75-4dd8-abd7-9a1ff7e11759](https://user-images.githubusercontent.com/90250848/187880414-bf236dec-fe91-4c62-8cbd-54a759472fa5.png)


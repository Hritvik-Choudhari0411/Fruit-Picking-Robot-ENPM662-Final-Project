# ENPM-662: INTRODUCTION TO ROBOT MODELLING PROJECT 2

## Technolgy Stack / Tools

<p align="left">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original-wordmark.svg" alt="python" width="70" height="70" />
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" alt="linux" width="70" height="70"/>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original-wordmark.svg" alt="opencv" width="70" height="70"/>
<img src="https://upload.wikimedia.org/wikipedia/commons/1/15/Robot_Operating_System_logo.svg" alt="ros" width="70" height="70"/>
</p>

## Installation

<!--

TODO

dependencis
-->

### Step 1: Get required folders
- copy the folders `basket_assmebly`, `husky` and `manipulator_v5` in the `{name of your catkin workspace}/src` folder

## Running

### Step 1: Build catkin
- open terminal window and run commands

```sh
cd {name of your catkin workspace}
catkin_make
source devel/setup.bash
```

### Step 2: Spawn robot in Gazebo

- open terminal and run the commands

```sh
roslaunch husky template_launch.launch
```
<p align="center">
<img src="https://github.com/Hritvik-Choudhari0411/Fruit-Picking-Robot-ENPM662-Final-Project/blob/main/images/spawn.png" width="500" height="400"/>
</p>

### Step 3: Run teleop code (chmod +x .py files if required)
- open new terminal window and run commands

```sh
cd src/husky/src
python3 teleop_template.py
```
The node will diaplay a message on how to controlthe robot as shown below:
```
Control Your Toy!
---------------------------
Moving around:
   u    i    o
   j    k    l
   m    ,    .
q/z : increase/decrease max speeds by 10%
w/x : increase/decrease only linear speed by 10%
e/c : increase/decrease only angular speed by 10%
space key, k : force stop
anything else : stop smoothly
CTRL-C to quit
```

use commands to reach a tree in the world

### Step 4: Command the manipulator
- open new terminal window

```sh
cd src/husky/src
python3 joint_pub.py

Note: The robot spawns with default configuration of all joint angles as 0 degrees
   Enter 1 for home configuration: to see the world
   Enter 2 for pick cofiguration: Pose for picking the fruit
   Enter 3 for place cofiguration: Pose to place picked fruit in basket
   Enter 0 to exit
```
<p align="center">
<img src="https://github.com/Hritvik-Choudhari0411/Fruit-Picking-Robot-ENPM662-Final-Project/blob/main/images/move.gif" width="500" height="400"/>
</p>

### Step 5: To see camera output in `rviz/rqt_image_view`
- open new terminal window

```sh
rviz
```

- add camera and subscribe to /image_raw topic
- (alternatively) run `rqt_image_view` and subscribe to `/image_raw` topic

## File Tree
```
hac_asaxena4_Project2
│   ├── basket_assembly
│   │   ├── CMakeLists.txt
│   │   ├── config
│   │   │   └── joint_names_basket_assembly.yaml
│   │   ├── export.log
│   │   ├── launch
│   │   │   ├── display.launch
│   │   │   └── gazebo.launch
│   │   ├── meshes
│   │   │   └── base_link.STL
│   │   ├── package.xml
│   │   ├── textures
│   │   └── urdf
│   │       ├── basket_assembly.csv
│   │       └── basket_assembly.urdf
│   ├── hac_asaxena4_Project2.pdf
│   ├── husky
│   │   ├── CMakeLists.txt
│   │   ├── config
│   │   │   ├── config_controllers.yaml
│   │   │   └── joint_names_husky.yaml
│   │   ├── export.log
│   │   ├── launch
│   │   │   ├── display.launch
│   │   │   ├── gazebo.launch
│   │   │   └── template_launch.launch
│   │   ├── meshes
│   │   │   ├── Back_L_lateral.STL
│   │   │   ├── Back_R_lateral.STL
│   │   │   ├── Chassis.STL
│   │   │   ├── Front_L_lateral.STL
│   │   │   ├── Front_R_lateral.STL
│   │   │   ├── wheel_FL.STL
│   │   │   ├── wheel_FR.STL
│   │   │   ├── wheel_LB.STL
│   │   │   ├── wheel_RB.STL
│   │   │   └── ydlidar.dae
│   │   ├── package.xml
│   │   ├── src
│   │   │   ├── dh_val.py
│   │   │   ├── joint_pub.py
│   │   │   ├── pub.py
│   │   │   ├── segment.py
│   │   │   ├── sub.py
│   │   │   └── teleop_template.py
│   │   ├── textures
│   │   ├── urdf
│   │   │   ├── bot_lidar_combined.urdf
│   │   │   ├── husky.csv
│   │   │   ├── husky_integration.urdf.xacro
│   │   │   ├── husky.urdf
│   │   │   └── ydlidar.urdf
│   │   └── worlds
│   │       ├── apple_farmV2.world
│   │       └── competition_arena.world
│   ├── manipulator_v5
│   │   ├── CMakeLists.txt
│   │   ├── config
│   │   │   └── joint_names_manipulator_v5.yaml
│   │   ├── export.log
│   │   ├── launch
│   │   │   ├── display.launch
│   │   │   └── gazebo.launch
│   │   ├── meshes
│   │   │   ├── base_link.STL
│   │   │   ├── joint2_link.STL
│   │   │   ├── joint3_link.STL
│   │   │   └── joint4_link.STL
│   │   ├── package.xml
│   │   ├── textures
│   │   └── urdf
│   │       ├── manipulator_v5.csv
│   │       └── manipulator_v5.urdf
│   ├── Project2_presentation.pptx
│   └── readme.md

```


## Credits

Hritivik Choudhari (hac@umd.edu)

Abhimanyu Saxena (asaxena4@umd.edu)

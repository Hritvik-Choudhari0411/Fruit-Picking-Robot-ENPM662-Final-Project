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

### Step 3: Run teleop code (chmod +x .py files if required)
- open new terminal window and run commands

```sh
cd src/husky/src
python3 teleop_template.py
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

### Step 5: To see camera output in `rviz/rqt_image_view`
- open new terminal window

```sh
rviz
```

- add camera and subscribe to /image_raw topic
- (alternatively) run `rqt_image_view` and subscribe to `/image_raw` topic


## Credits

Hritivik Choudhari (hac@umd.edu)

Abhimanyu Saxena (asaxena4@umd.edu)

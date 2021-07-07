# Turtlebot3-with-SLAM
PC setup to run TurtleBot3 in Gazebo simulation using ROS pachages.
These packages were tested under ROS melodic, Ubuntu 18.04, and Gazebo version 9.
The TurtleBot3 robot uses SLAM (Simultaneous localization and mapping) to navigate through the world. 
In this project, I used the TurtleBot3 waffle model and turtlebot3_world.

here is a temporary link to the Turtlebot3 with SLAM project on ROS online workspace:
    https://app.theconstructsim.com/#/l/417724bc/
    Expires at 2021-07-10 14:46

## Dependencies
Assuming you have installed ROS, run these lines in the terminal:

        $ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
        ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
        ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
        ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
        ros-melodic-rosserial-server ros-melodic-rosserial-client \
        ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
        ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
        ros-melodic-compressed-image-transport ros-melodic-rqt* \
        ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
Install TurtleBot3 Packages:

        $ sudo apt-get install ros-kinetic-dynamixel-sdk
        $ sudo apt-get install ros-kinetic-turtlebot3-msgs
        $ sudo apt-get install ros-kinetic-turtlebot3
Set the model name:

        $ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
Sometimes ROS is not configuring the the added files, so it is recommended to write this command:

        $ source ~/.bashrc
        
## Usage
Install Simulation Package:

        $ cd ~/catkin_ws/src/
        $ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
        $ cd ~/catkin_ws && catkin_make
To run TurtleBot3 on gazebo + the world:

        $ export TURTLEBOT3_MODEL=waffle
        $ roslaunch turtlebot3_gazebo turtlebot3_world.launch
      
<img width="646" alt="Screen Shot 2021-07-06 at 5 34 37 PM" src="https://user-images.githubusercontent.com/85841915/124713656-812f6a00-df09-11eb-9212-2840f2ea1e76.png">

        
To control the movement of the robot with the keyboard:

        $ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
        
<img width="393" alt="Screen Shot 2021-07-06 at 5 37 35 PM" src="https://user-images.githubusercontent.com/85841915/124713746-96a49400-df09-11eb-9676-33da62f2755b.png">

## issues
Gazebo simulator needs huge computation capabilities. it causes the computer to run slowly then crash. In my case, I switch my project to ROS online workspace. and the performance was great. Also, when I was working with the VB, I couldn't solve the "there is no enough space" issue. None of the listed solutions worked for me. Therefore, I made a new virtual hard disk and that was successful. However, when you using ROS online workspace you don't have to worry about the available space.



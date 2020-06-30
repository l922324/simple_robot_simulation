# simple_robot_simulation
This is a simple robot simulation simulating a two wheel drive mobile robot with one castor wheel in front in a simple gazebo environment. This simulation requires a proper installed ROS, gazebo and rviz.

This simulation package was created under following environment:

**OS version: Ubuntu 16.04**

Download address: http://releases.ubuntu.com/16.04/

**ROS version: Kinetic**

Installation guidance: http://wiki.ros.org/kinetic/Installation/Ubuntu

**Gazebo version: Gazebo10**

Install gazebo in ubuntu: http://gazebosim.org/tutorials?tut=install_ubuntu&cat=install

Install gazebo_ros_pkgs: http://gazebosim.org/tutorials?tut=ros_installing&cat=connect_ros

**Rviz version: rviz 1.12.17**
```
sudo apt-get install ros-kinetic-rviz 
```
**Robot movement keyboard control: teleop-twist-keyboard**
```
sudo apt-get install ros-kinetic-teleop-twist-keyboard
```
**Steps of running this simulation**
1. In terminal, creat workspace
```
mkdir catkin_ws
cd catkin_ws
mkdir src
cd src
catkin_init_workspace
```
2. Clone this package into /src directory
```
git clone https://github.com/l922324/simple_robot_simulation.git
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```
3. Roslaunch robot body into gazebo
```
roslaunch simple_robot_gazebo simple_robot.launch 
```
4. Open another terminal window, visualize lidar data in Rviz
```
roslaunch simple_robot_rviz simple_robot_rviz.launch
```
5. Open another terminal window, run teleop_twist_keyboard to control movement of robot in gazebo
```
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```
Play the robot around by pressing “i” to move forward, “,” to move backward etc.

### Update 2020.06.24

1. While installing ROS kinetic desktop using 
```
sudo apt-get install ros-kinetic-desktop-full 
```
Gazebo7.x and RVIZ will be installed automatically, tested the program can also work with Gazebo7.x, hence Gazebo10 is not necessary to be installed.

2. If Gazebo7.x has problem of opening on its own or showing error `VMware: vmw_ioctl_command error Invalid argument.`, might be problem of VMware, run 
```
export SVGA_VGPU10=0 
```
To make it permanent 
```
echo "export SVGA_VGPU10=0" >> ~/.profile
```

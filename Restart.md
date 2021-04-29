### 1. Downlaod Chrome
Download GDebi first 
### 2. Download ROS-Noetic
### 3. Download moveit
When run 
```
catkin config --extend /opt/ros/${ROS_DISTRO} --cmake-args -DCMAKE_BUILD_TYPE=Release*
```
Error:
*The 'osrf-pycommon>0.1.1' distribution was not found and is required by catkin-tools* 

Solution:
```
sudo apt install python3-catkin-tools python3-osrf-pycommon
```
### 4. ROS control
```
sudo apt-get install ros-noetic-ros-control ros-noetic-ros-controllers
```

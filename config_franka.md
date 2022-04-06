# config_franka
How to complie franka in personal laptop.

### Check Compatible Versions 
* Check the franka system version on Desk

  The system version of panda3 is 4.2.0

* Check the compatible version/branch of libpanda

  [libfranka change log](https://frankaemika.github.io/docs/libfranka_changelog.html).
  Here we choose libfranka 0.8.0, compatible with Ubuntu 20.04 and ROS noetic.

* Check the compatible version/branch of franka_ros

  [panda_ros change log](https://frankaemika.github.io/docs/franka_ros_changelog.html).
  Here we choose franka_ros 0.8.2, compatible with ROS nortic.



### Set Real-time Kernel
* Follow the [instruction](https://frankaemika.github.io/docs/installation_linux.html). Don't forget to give real time permission. 
* Config the grub2 to list all kernels when booting:
  ```
  $ sudo nano /etc/default/grub
  ```
  Change the following parameters:
  ```
  GRUB_TIMEOUT_STYLE=menu
  GRUB_TIMEOUT=10
  GRUB_TERMINAL=console
  ```
  ```
  $ sudo update-grub
  ```

### Control Franka with Moveit
* Install the netic version of [Moveit](https://ros-planning.github.io/moveit_tutorials/).
* Run franka_ros with trajectory controller. In 'franka_ros/franka_control/launch/franka_control.launch', add the following line:
  ```
  <node name="state_controller_spawner_1" pkg="controller_manager" type="spawner" respawn="false" output="screen" args="position_joint_trajectory_controller"/>
  ```
  ```
  $ roslaunch roslaunch franka_control franka_control.launch robot_ip:=192.168.2.105 arm_id:=panda
  ```
* Change the 'demo.launch' in panda_moveit_config, switch off the fake execution:
  ```
  <arg name="fake_execution" value="false"/>
  ```
* Run demo.launch under moveit workspace.
  ```
  roslaunch panda_moveit_config demo.launch
  ```

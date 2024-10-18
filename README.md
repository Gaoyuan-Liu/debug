# Debug
A note of debug work

## 1. Install ROS melodic

## 2. Install git
```$ sudo apt install git```

## 3. Copy boost to the usr/local/include

## 4. Write the quadrotor_plugins.gazebo.xacro 

## 5. Add the grass:
In the gazebo_world_materials, copy the "my_ground_plane" to ~/.gazebo/models folder.

## 6. Change the default python version:
```
$ update-alternatives --list python
```
show all the version.
```
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7  1
```
```
$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.6  2
```
set the priority of different versions.
```
$ sudo update-alternatives --config python
```

## 7. No rospy/rospkg packages when using python3
```
$ pip3 install rospkg
```

## 8. Where is the python package go?
/opt/ros/melodic/lib/python2.7/dist-packages/
/usr/local/lib/python3.6/dist-packages/
.local/lib/python2.7/site-packages
.local/lib/python3.6/site-packages

## 9. ModuleNotFoundError: No module named 'defusedxml'?
```
$ pip install defusedxml
```
or
```
$ sudo apt-get install python-defusedxml
```
## 10. Original zbook's name:
liu-HP-ZBook-Fury-15-G7-Mobile-Workstation

## 11. Cannot find boost:
boost is in "/usr/include", but Cmake try to find boost in "/usr/local/include"
Go there and copy it to:
```
$ sudo cp -r boost /usr/local/include
```
## 12. Connect to VUBnext wifi:
* Security: WAP & WAP2 Enterprise
* Authentication: Protected EAP (PEAP)
* Anonymous identity: 
* PEAP version: Automatic
* Inner authentication: MSCHAPv2
* Username: gaoyliu
* Password: Liu_1994

## 13. How to build a virtual environment:
```
$ virtualenv --python=/usr/bin/python2.6 <path/to/new/virtualenv/>'
```
```
source venv3.8/bin/activate
```
```
deactivate
```

## 15. Python3 catkin build error
Unable to find either executable 'empy' or Python module 'em'...  try installing the package 'python-empy'
```
catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3
```
## 16. Conda and rospkg conflict
```
conda install -c conda-forge rospkg
```
## Xserver
```
sudo apt-get remove --purge xserver-xorg
```
```
sudo apt-get install xserver-xorg
```
```
sudo dpkg-reconfigure xserver-xorg
```
## Delete nvidia
```
sudo apt-get purge nvidia*
```
## Install nvidia driver
```
sudo ubuntu-drivers install
```


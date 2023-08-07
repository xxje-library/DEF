# Introduction
This library has been my learning experience for a period of time, and I have made countless mistakes and still haven't learned well in many aspects. The basic learning process is described here.  
## ROS learning  
In my experience, ROS does not require deliberate learning. What we need to do is learn how to use ROS. Therefore, as long as we start to understand the usage of ROS and understand the mechanism of ROS messages, we can handle the vast majority of tasks. The rest only require us to learn while using ROS. 

Here are some links related to ROS learning：  
1.[wiki](http://wiki.ros.org/ROS/Tutorials)  
2.[古月居](https://www.bilibili.com/video/BV1zt411G7Vn/?spm_id_from=333.337.search-card.all.click&vd_source=d6ea4dbc61d9452fed12a5669810253d)  
## Opencv and PCl  
These two libraries do not need to be deliberately studied, just learned during use. We use the version that comes with the system for PCL. We can install opencv in “ /additional bag " folder. First, extract it and enter the folder:
```bash
cd opencv
madir build
cd build && cmake ..
make -j8
sudo make install
```

## How to use the current repository  
This library is actually pieced together by many corresponding libraries, using many libraries, resulting in a relatively awkward situation. And the implementation effect is not particularly good, in fact, it may be an essential starting point design issue, and the first step is to build the corresponding simulation environment.  
### GAZEBO Environment  
```bash
git clone -b v1.12.3 https://github.com/PX4/PX4-Autopilot.git --recursive     
```
add the bashrc file  
```bash
source ~/PX4-Autopilot/Tools/setup_gazebo.bash ~/PX4-Autopilot/ ~/PX4-Autopilot/build/px4_sitl_default
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:~/PX4-Autopilot
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:~/PX4-Autopilot/Tools/sitl_gazebo
source ~/.bashrc
```
We use iris_depth_camera model and the world which is chose by you. you can see the model in " ~/PX4-Autopilot/Tools/sitl_gazebo/models " and world in " ~/PX4-Autopilot/Tools/sitl_gazebo/worlds ". The initial file connection to Mavros is in " ~/PX4-Autopilot/launch " which is called " mavros_posix_sitl.launch ". As show in the picture, you can change the position, orientation and model,world. [Mavros](http://wiki.ros.org/mavros) is a secondary wrapper used for controlling drones and onboard computers. There are somethings about it.  






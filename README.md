# laser
## #Hokuyo激光雷达的使用  

### 1.下载urg_node 及相关支持包

  

```
  source /opt/ros/indigo/setup.bash
  mkdir -p ~/catakin_ws/src
  cd ~/catkin_ws/src
  catkin_init_workspace
  cd ..
  catkin_make
```

```
 cd ~/catkin_ws/src
 git clone https://github.com/ros-perception/laser_proc.git
 git clone https://github.com/ros-drivers/urg_c.git
 cd ..  
 catkin_make
```

```
 cd ~/catkin_ws/src
 git clone https://github.com/ros-drivers/urg_node
 cd ~/catkin_ws
 catkin_make
 catkin_make install
```

### 2.修改IP

```
  sudo nano /etc/network/interfaces
  auto eth0
  allow-hotplug eth0
  iface eth0 inet static
  address 192.168.0.1
  netmask 255.255.255.0
```

  **网络右键同样需要修改**

###  3.测试

 rosrun urg_node urg_node _ip_address:=192.168.0.10  
 rviz  

## #velodyne vlp16激光雷达使用（192.168.1.201）

### 1.配置ip

  192.168.1.77  255.255.255.0

### 2.安装依赖

```
  sudo apt-get install ros-noetic-velodyne
```



### 3.创建项目文件

```
  mkdir -p catkin_velodyne/src
  cd catkin_velodyne/src
  git clone https://github.com/ros-drivers/velodyne.git
  cd ..
  catkin_make
  source devel/setup.bash
```



### 4.测试  

```
  roslaunch velodyne_pointcloud VLP16_points.launch
  rosrun rviz rviz -f velodyne
```

  


# bar30_sensor_ros2
This repository is UW's Bar30 depth sensor ROS2 package

## Requirements
[Bar30 Depth/Pressure Sensor](https://underwaterdrone.stores.jp/items/6281b648b5285a0e96ed312b?_gl=1*119sjd4*_ga*MTk2MzkxMTc2OC4xNjU0OTM0NTkw*_ga_8RLDMYVT90*MTY2NDM1NTI3MC4xMy4xLjE2NjQzNTUyNzguNTIuMC4w)

[Bar30 module](https://github.com/bluerobotics/ms5837-python)

## Installation
Build from source and install ROS environments. Please see ROS Wiki.

Create ros2 workspace
```
mkdir -p ~/dev_ws/src
```

Download the packages for bar30 using git.
```
cd ~/dev_ws/src
git clone https://github.com/tasada038/ms5837_node.git
```

Also, clone ms5837-python packages via bluerobotics, and copy ms5837 module
```
git clone https://github.com/bluerobotics/ms5837-python
cp -a ms5837-python/ms5837 ms5837_node/ms5837_node/
```

Please build after installing the library required for ms5837-python

```
cd..
colcon build
```

## Usage
```
ros2 launch ms5837_node bar30_launch.py
```

If you want to know the depth in **meters**, run the following node.
```
ros2 run ms5837_node convert_depth_data
```

## Published Topics
sensor_msgs.msg FluidPressure: bar30/pressure

sensor_msgs.msg Temperature: bar30/temperature

std_msgs.msg Float32: bar30/depth

nav_msgs.msg Odometry: bar30/odom


## License
This repository is licensed under the MIT license, see LICENSE.
# bobac3 车辆模型使用方法

## 安装依赖

```bash
sudo apt install ros-noeitc-gmapping
sudo apt install ros-noetic-teleop-twist-keyboard
sudo apt install ros-noetic-map-server
sudo apt install ros-noetic-navigation
```


## 文件编译

```bash
cd bobac
rm -rf build/ devel/
catkin_make
```

## 加载机器人模型和仿真环境

```bash
source devel/setup.bash
roslaunch bobac3_description gazebo.launch
```

## 建图

先打开一个终端，加载机器人模型和仿真环境。
再打开另一个终端运行建图程序

```bash
source devel/setup.bash
roslaunch bobac3_nav map.launch
```

再打开另外一个终端，用于控制小车建图

```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

建图完之后，再打开另外一个终端，保存地图

```bash
source devel/setup.bash
roslaunch bobac3_nav map_saver.launch
```

## 定位

先打开一个终端，加载机器人模型和仿真环境。
再打开另一个终端运行定位程序

```bash
source devel/setup.bash
roslaunch bobac3_nav amcl.launch
```

然后通过rviz上的`2D Pose Estimate`指定机器人在仿真中的初始位置，就可以定位了


## 导航

先打开一个终端，加载机器人模型和仿真环境。
再打开另一个终端运行导航程序

```bash
source devel/setup.bash
roslaunch bobac3_nav nav.launch
```
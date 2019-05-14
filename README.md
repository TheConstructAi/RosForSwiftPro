# RosForSwiftPro
This is ROS package for swift pro started by ufactory team.
These packages support Moveit!, RViz and serial communication for swift pro.

# Requirement
- ROS

# Download and install
Download ros packages for uarm swift pro
```bash
cd ~/catkin_ws/src
git clone https://github.com/asukiaaa/RosForSwiftPro.git
```

Install all dependencies
```bash
rosdep install --from-paths ./ -i
```

Compile
```bash
catkin_make
```

Load
```bash
source ~/catkin_ws/devel/setup.bash
```

# Simulation
Connect your swift/swiftpro to computer and get USB permission to access uArm
```bash
sudo chmod 666 /dev/ttyACM0
```

## Display mode: Get data from swiftpro
Get data from serial and simulate swiftpro in RViz.
```bash
roslaunch swiftpro pro_display.launch
```
You can drag your swiftpro and it will simulate in Rviz.

## Control Mode: Send data to swiftpro
Connect swiftpro, send data though serial.
```bash
roslaunch swiftpro pro_control.launch
```
Open another ternimal to get joint angles from Moveit!.
```bash
roslaunch pro_moveit_config demo.launch
```
You can do trajectory planning or grasping in moveIt!.

# RosForSwiftPro
This is ROS package for swift pro started by ufactory team.
These packages support Moveit!, RViz and serial communication for swift pro.

# Download and install
Download ros packages for uarm swift pro
```bash
cd ~/catkin_ws/src
git clone https://github.com/asukiaaa/RosForSwiftPro.git
```

Install dependencies using rosdep
If running the rosdep for the first time start by running:
```bash
sudo rosdep init
rosdep update
```
Then install all dependencies using:
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
right now, you can drag your swiftpro and it will simulate in Rviz.

## Control Mode: Send data to swiftpro
Connect swiftpro, send data though serial.
```bash
roslaunch swiftpro pro_control.launch
```
Open another ternimal to get joint angles from Moveit!.
```bash
roslaunch pro_moveit_config demo.launch
```
right now, you can do trajectory planning or grasping in moveIt!.

# Message example
SwiftproState.msg: includes all data about swiftpro
```
float64 motor_angle1
float64 motor_angle2
float64 motor_angle3
float64 motor_angle4
float64 x
float64 y
float64 z
uint8   pump
uint8   swiftpro_status
uint8   gripper
```
position.msg: includes x, y, z information(mm)
```
float64 x
float64 y
float64 z
```
angle4th.msg: 4th motor angle(degree)
```
float64 angle4th
```
status.msg: work if 1; otherwise 0
```
uint8 status
```

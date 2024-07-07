# 2-DOF-Robotics-manipulator-Control-with-Ros2-Humble

### System Check Commands

To check the system configuration and ROS setup, run the following commands:

## Download Necessary Packages and Prepare the System Environment

Update and upgrade the system packages:

```bash
sudo apt update
sudo apt upgrade
```

Install necessary packages:

```bash
sudo apt-get install gedit
sudo apt install ros-humble-robot-state-publisher
sudo apt install ros-humble-joint-state-publisher
sudo apt install ros-humble-joint-state-publisher-gui
```

Verify `rviz2` installation:

```bash
ros2 pkg prefix rviz2
```

### Package Descriptions

- **robot-state-publisher**: Publishes 3D poses of the robot links using a kinematic tree of the robot based on joint angles/displacements.
- **joint-state-publisher**: Publishes joint states as messages of type `sensor_msgs/JointState`.
- **joint-state-publisher-gui**: Graphically sets and publishes joint state values for a given URDF model.

### Additional Information

- **tf2**: A transform library that tracks the relationship between coordinate frames over time, maintaining a tree structure of coordinate frames relationships.

## Creating the Workspace and Packages

Create the workspace and initialize the package structure:

```bash
mkdir -p ~/ws_humble_urdf/src
cd ~/ws_humble_urdf/
colcon build
cd ~/ws_humble_urdf/src
ros2 pkg create --build-type ament_cmake urdf_humble_test
```

Navigate to the newly created package directory:

```bash
cd urdf_humble_test
ls -l
# Output should show:
# - include
# - CMakeLists.txt
# - src
# - package.xml
```

Create necessary directories:

```bash
mkdir launch urdf config
ls -l
# Output should show:
# - include
# - CMakeLists.txt
# - src
# - package.xml
# - launch
# - config
# - urdf
```

Build the workspace:

```bash
cd ~/ws_humble_urdf/
colcon build
```

## Build and Run the RViz

Source the workspace and launch the RViz:

```bash
source ~/ws_humble_urdf/install/setup.bash
ros2 launch urdf_humble_test display.launch.py
```


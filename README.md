# Realsense2 Description

**Note:** This is a fork of the [issaiass/realsense2_description repository](https://github.com/issaiass/realsense2_description).

### Prerequisites

Install the `realsense_gazebo_plugin` package by following the [linked instructions](https://github.com/troiwill/realsense_gazebo_plugin#installation).

### Installation

Clone this repository in your catkin workspace and then build.
```
# Make a catkin workspace.
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src

# Clone the repository.
git clone https://github.com/troiwill/realsense2_description.git

# Build
cd ../
catkin build
source devel/setup.bash
```

### Run the D435 + Rviz + Gazebo Demo

Run the following command to spawn a D435 camera in Gazebo anr run Rviz.
```
roslaunch realsense2_description view_d435_model_rviz_gazebo.launch
```

Please ensure that you see the camera topics published by the camera.
```
rostopic list
```

### Camera Calibration

Install the `calibration_gazebo` ROS package so that you can calibrate your simulated camera in Gazebo.
```
cd ~/catkin_ws/src
git clone https://github.com/oKermorgant/calibration_gazebo
cd ../
catkin build
source devel/setup.bash
```


### Converting a .xacro file to SDF

If you need to attach one of these cameras to an SDF file, you may need to convert the camera `*.xacro` file to `*.sdf`.
Here are the instructions to produce an SDF.
```
xacro test_d435_camera.urdf.xacro > test_d435_camera.urdf
gz sdf -p test_d435_camera.urdf > test_d435_camera.sdf
```

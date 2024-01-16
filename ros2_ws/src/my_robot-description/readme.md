# Create launch file start robot state publsiher with URDF

```bash
<launch>
    <let name="urdf_path"
         value="$(find-pkg-share my_robot-description)/urdf/robot-wheel.urdf" />
    <node pkg="robot_state_publisher" exec="robot_state_publisher">
         <param name="robot_description"
                value="$(command 'xacro $(var urdf_path)')"/>
    </node>

    <node pkg="joint_state_publisher_gui" exec="joint_state_publisher_gui"/>

    <node pkg="rviz2" exec="rviz2" output="screen"/>
</launch>
# Here in let tag find urdf file path in pkg  and use this as parameter of value of robot_description
cd ros2_ws
colcon build
 ros2 launch my_robot-description display.launch.xml

```

## Add default Robotmodel and Tf in rviz config

1. save rviz file to any directory
2. Apply below command

```bash
ros2 run rviz2 rviz2 -d ~/Documents/my_robot.rviz


```

## Add Rivz config in launch file

1. create rviz folder in pkg directory
2. paste config file in this folder
3. Add in CMakelists install rviz

```bash
# create variable for rviz path
     <let name="rviz_config"
          value="$(find-pkg-share my_robot-description)/rviz/my_robot.rviz"/>
# Add this variable in rviz node as a arguments
 <node pkg="rviz2" exec="rviz2"  output="screen"
          args="-d $(var rviz_config)"
    />

```

# Make the URDF Compatible with xacro

### Install xacro

```bash
sudo apt install ros-humble-xacro
```

1. Rename the Urdf file with "urdf.xacro" extension or just "xacro" extnsion
2. changes in urdf file in robot start tag as like :

```bash
<robot name="my_robot" xmlns:xacro="http://www.ros.org/wiki/xacro">

```

3. Rename urdf file path in launch file and again colcon build.

# Create Veraible with Xacro properties

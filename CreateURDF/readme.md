# URDF (Unified Robot Description Format)

# rpy

1. roll is the rotation on x axis
2. pitch is the rotation on y axis
3. yaw is the rotation on z axis

# create basic urdf file

```bash

<?xml version="1.0" ?>
<robot name="my_robot">
    <link name="base_link">
        <visual>
            <geometry>
                <box size="0.6 0.4 0.2"/>
            </geometry>
            <origin xyz="0 0 0" rpy="0 0 0" />
        </visual>
    </link>
</robot>

# open terminal and run this command
ros2 launch urdf_tutorial display.launch.py model:=/home/emon/development/ros2-beginners-level-2/CreateURDF/my_robot.urdf

### Joint TF .Joint need to relation between two frames where one is root link and another is child link.

### In Joint tag required a parent tag and chiled tag
    <joint name="base_second_joint" type="fixed" >
        <parent link="base_link"/>
        <child link="second_link"/>
        <origin xyz="0 0 0" rpy="0 0 0"/>
    </joint>



```

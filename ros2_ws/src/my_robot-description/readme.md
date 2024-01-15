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

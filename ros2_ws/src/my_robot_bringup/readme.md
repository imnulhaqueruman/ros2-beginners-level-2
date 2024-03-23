```bash

 <!-- <include file="$(find-pkg-share gazebo_ros)/launch/gazebo.launch.py" /> instead thsi open a new terminal
        and run  gazebo --verbose -s libgazebo_ros_factory.so


    -->
```
# Launch The robot in the world 
```bash

ros2 launch my_robot_bringup my_robot_gazebo.launch.xml 


```
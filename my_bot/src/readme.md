## First Launch 
```bash 
# 1st terminal 
ros2 launch my_rover rsp.launch.py
#2nd terminal 
ros2 run rviz2 rviz2
#3rd terminal 
ros2 run joint_state_publisher_gui joint_state_publisher_gui

```
## Spawning our robot in Gazebo

```bash
# 1st terminal 
ros2 launch my_rover launch_sim.launch.py
# 2nd terminal 
ros2 launch gazebo_ros gazebo.launch.py

# 3rd Terminal 
ros2 run teleop_twist_keyboard teleop_twist_keyboard

# 4th terminal 
ros2 run joint_state_publisher_gui joint_state_publisher_gui

```

## Launch Depth Camera 

```bash
#1st terminal 

ros2 launch my_rover launch_sim.launch.py world:=./src/my_rover/worlds/obstacle.world

#2nd Terminal 
ros2 run rviz2 rviz2 
# add Robot model --> select topic -- robot_description 
# add image --> select topic --> /camera/depth/image_raw
# add pointcloud2 --> select topic --> /camera/points 

# 3rd terminal 
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```
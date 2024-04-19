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

## Slam_tollbox 

```bash
sudo apt install ros-humble-slam-toolbox
```
```bash
# Copy to config file 
cp /opt/ros/humble/share/slam_toolbox/config/mapper_params_online_async.yaml ~/development/ros2-beginners-level-2/my_bot/src/my_rover/config/


```
1. 
```bash 
ros2 launch my_rover launch_sim.launch.py world:=./src/my_rover/worlds/obstacle.world

```
2. 
```bash
ros2 run rviz2 rviz2 -d ~/src/my_rover/config/main.rviz

```
3. Slam launch 

```bash
cd ~/development/ros2-beginners-level-2/my_bot
ros2 launch slam_toolbox online_async_launch.py params_file:=./src/my_rover/config/mapper_params_online_async.yaml use_sim_time:=true

```
4. ros2 run teleop_twist_keyboard teleop_twist_keyboard

# Install Nav2 
```bash
sudo apt install \
  ros-$ROS_DISTRO-navigation2 \
  ros-$ROS_DISTRO-nav2-bringup \
  ros-$ROS_DISTRO-turtlebot3*

```
# Run map server 
```bash
ros2 run nav2_map_server map_server --ros-args -p yaml_filename:=my_map_save.yaml -p use_sim_time:=true

# other terminal 

ros2 run nav2_util lifecycle_bringup map_server 

# Run amcl 
 ros2 run nav2_amcl amcl --ros-args -p use_sim_time:=true

 # Run life cylce for amcl 

 ros2 run nav2_util lifecycle_bringup amcl

```

# Nav2 

1. sudo apt install ros-humble-twist-mux
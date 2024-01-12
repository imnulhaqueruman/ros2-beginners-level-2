# Install TF packages

```bash

sudo apt install ros-humble-urdf-tutorial

# Setup envrionment
source /opt/ros/humble/setup.bash

gedit ~/.bashrc
# Add the following line at the end of the file and save it
source /opt/ros/humble/setup.bash

# After install any ros package to find it by this command
cd /opt/ros/humble/share

cd /opt/ros/humble/share/urdf_tutorial/urdf

# Then applied command to launch ros file to visualize rviz
ros2 launch urdf_tutorial display.launch.py model:=/opt/ros/humble/share/urdf_tutorial/urdf/08-macroed.urdf.xacro

# Another tf2 packages should be installed to see relationship between tfs and tf tree
sudo apt install ros-humble-tf2-tools

# Then run
ros2 run tf2 tools view frames



```

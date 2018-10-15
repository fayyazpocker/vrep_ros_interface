# ROS Interface plugin for V-REP

### Compiling

1. Make sure you have set your V_REP ROOT, if not open your bashrc file and add the following code
```
export VREP_ROOT="/path_of_vrep_folder"
```
2. Go to the src directory in catkin workspace and clone this directory
3. Use *catkin_make* to build the raw source code. 
4. Use *source devel/setup.bash* to have access to the ROS commands
5. If you have to use new ros-messages of other packages in your V-REP scene, all you have to do is to add that message to *vrep_ros_interface/meta/messages.txt*.
For instance, if there is a ROS package named *pid_tune* in which there is a ros message called *testing.msg*, in order to use that rosmsg in your V-REP scene, you will have to add *pid_tune/testing* in *messages.txt*
6. If you have to add new message in the *vrep_ros_interface* package itself,create a new message in msg folder of type .msg say *new.msg* but make sure you add the message in the CMakeLists.txt in vrep_ros_interface package
```
add_message_files(FILES new.msg)
```
7. Compile
```
$ catkin make
```
8. In order to copy the new .so file generated, open the vrep_ros_interface package in src directory and type
```
./install.sh
```

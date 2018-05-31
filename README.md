# ROS Interface plugin for V-REP

### Compiling

_NOTE:_ the directory containing all files (i.e. package.xml etc) must be called vrep_ros_interface, otherwise build will fail.

1. Install required packages for [v_repStubsGen](https://github.com/CoppeliaRobotics/v_repStubsGen): see v_repStubsGen's [README](external/v_repStubsGen/README.md)
2. Checkout
```
$ git clone --recursive https://github.com/CoppeliaRobotics/v_repExtRosInterface.git vrep_ros_interface
```
On recursive command, the git repository of v_repStubsGen and v_repPlusPlus also gets cloned

3. Make sure you have set your V_REP ROOT, if not open your bashrc file and add the following code
```
export VREP_ROOT="/path_of_vrep_folder"
```
4. To add messages, create a new message in msg folder of type .msg....but make sure you add the message in the CMakeLists.txt in vrep_ros_interface package
```
add_message_files(FILES your_msg.msg)
```

5. Edit `meta/messages.txt` and `meta/services.txt` if you need to include more ROS messages/services. You need to specify the full message/service type, i.e. geometry_msgs/Twist rather than Twist.

6. Compile
```
$ catkin make
```
7. In order to copy the new .so file generated, open the vrep_ros_interface package in src directory and type
```
./install.sh
```

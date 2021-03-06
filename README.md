# SERO
Contains code used in SERO: The humanoid service robot.

Contributors:
Aasheesh Singh
Madhav Aggarwal
Mohd. Ismail Khan
Mohd. Suhail


To setup arduino with ROS:

1. arduino
2. roscore
3. rosrun rosserial_python serial_node.py /dev/ttyACM1
4. rostopic list

To start teleop operation

1. source ~/catkin_ws2/devel/setup.bash
2. roslaunch turtlebot_teleop keyboard_teleop.launch


To start base_controller.cpp

1. rosrun my_personal_robotic_companion base_controller catkin_ws2/src/my_personal_robotic_companion/my_personal_robotic_companion/src/base_controller.cpp


To run Gazebo

1.  roslaunch turtlebot_gazebo turtlebot_world.launch


For Kinnect

1. roslaunch openni_launch openni.launch
2. rosrun depthimage_to_laserscan depthimage_to_laserscan image:=/camera/depth/image_raw
3. source ~/catkin_ws2/devel/setup.bash
4. roscd my_personal_robotic_companion/
5. roslaunch ./launch/kinect_laser.launch *not to be done

*instead of running above commands, when robot_config is launched then, freenect, depth to laser are run


To launch slam

1. roscd my_personal_robotic_companion/	
2. roslaunch ./launch/slam.launch		// it includes robot_config.launch launching

To launch gyro.py

1.  cd ~/catkin_ws2/src/my_personal_robotic_companion/my_personal_robotic_companion/scripts/
2. python gyro.py

To view TF frame tree

1. rosrun tf view_frames
2. evince frames.pdf
or
1, rosrun rqt_tf_tree rqt_tf_tree



Website : http://www.hessmer.org/blog/2011/04/10/2d-slam-with-ros-and-kinect/


Hokuyo Laser launch:

gyro.py
roslaunch my_personal_robotic_companion laser_config.launch
roslaunch hokuyo_node hokuyo_test.launch
roslaunch ./launch/slam_laser.launch

Launching RTAB map
roslaunch openni_launch openni.launch depth_registration:=true
roslaunch rtabmap_ros rtabmap.launch rtabmap_args:="--delete_db_on_start"



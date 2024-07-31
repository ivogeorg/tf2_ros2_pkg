```
user:~$ ros2 launch tf2_ros2_pkg start_tf_fixes.launch.xml
[INFO] [launch]: All log files can be found below /home/user/.ros/log/2024-07-31-02-00-48-517968-1_xterm-10111
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [static_transform_publisher-1]: process started with pid [10113]
[INFO] [cam_bot_odom_to_tf_pub_late_tf_fixed.py-2]: process started with pid [10115]
[INFO] [cam_bot_move.py-3]: process started with pid [10117]
[static_transform_publisher-1] [INFO] [1722391248.852694628] [static_transform_publisher_turtle_odom]: Spinning until killed publishing transform from 'world' to 'odom'
[cam_bot_odom_to_tf_pub_late_tf_fixed.py-2] [WARN] [1722391249.304322192] [odom_to_tf_broadcaster_node]: odom_to_tf_broadcaster_node READY!
[cam_bot_move.py-3] [INFO] [1722391249.393196432] [cam_bot_move_node]: SetEntityState service READY...
[cam_bot_move.py-3] [ERROR] [1722391254.394852171] [cam_bot_move_node]: Could not transform world to carrot: "carrot" passed to lookupTransform argument source_frame does not exist.
[cam_bot_move.py-3] [INFO] [1722391254.395513839] [cam_bot_move_node]: 3 -- POSE DEST=None
[cam_bot_move.py-3] [WARN] [1722391254.396012636] [cam_bot_move_node]: No Coordinates available yet...
[cam_bot_move.py-3] [INFO] [1722391254.396380564] [cam_bot_move_node]: Moved the Robot to frame =carrot
[cam_bot_move.py-3] [ERROR] [1722391259.394466520] [cam_bot_move_node]: Could not transform world to carrot: "carrot" passed to lookupTransform argument source_frame does not exist.
[cam_bot_move.py-3] [INFO] [1722391259.395167552] [cam_bot_move_node]: 3 -- POSE DEST=None
[cam_bot_move.py-3] [WARN] [1722391259.397998903] [cam_bot_move_node]: No Coordinates available yet...
[cam_bot_move.py-3] [INFO] [1722391259.398630466] [cam_bot_move_node]: Moved the Robot to frame =carrot
^C[WARNING] [launch]: user interrupted with ctrl-c (SIGINT)
```

```
[cam_bot_move.py-3] [INFO] [1722393590.555433663] [cam_bot_move_node]: 1 -- type translation_pose=<class 'geometry_msgs.msg._vector3.Vector3'>
[cam_bot_move.py-3] [INFO] [1722393590.555856140] [cam_bot_move_node]: 2 -- type rotation_pose=<class 'geometry_msgs.msg._quaternion.Quaternion'>
[cam_bot_move.py-3] [INFO] [1722393590.556305950] [cam_bot_move_node]: 3 -- POSE DEST=geometry_msgs.msg.Pose(position=geometry_msgs.msg.Point(x=-0.4030151852484344, y=-0.6103458741149066, z=0.5099975091832043), orientation=geometry_msgs.msg.Quaternion(x=-0.254293467734348, y=0.23003733073797067, z=0.6967554606277131, w=0.6300392740298439))
[cam_bot_move.py-3] [INFO] [1722393590.557373495] [cam_bot_move_node]: 4 -- STATE to SEND=gazebo_msgs.msg.EntityState(name='cam_bot', pose=geometry_msgs.msg.Pose(position=geometry_msgs.msg.Point(x=-0.4030151852484344, y=-0.6103458741149066, z=0.5099975091832043), orientation=geometry_msgs.msg.Quaternion(x=-0.254293467734348, y=0.23003733073797072, z=0.6967554606277131, w=0.6300392740298439)), twist=geometry_msgs.msg.Twist(linear=geometry_msgs.msg.Vector3(x=0.0, y=0.0, z=0.0), angular=geometry_msgs.msg.Vector3(x=0.0, y=0.0, z=0.0)), reference_frame='world')
[cam_bot_move.py-3] [INFO] [1722393590.557881261] [cam_bot_move_node]: Moved the Robot to frame =front_turtle_frame
```


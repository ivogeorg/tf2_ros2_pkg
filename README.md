### tf2_ros2_pkg

#### Useful command-line tools

1. `ros2 run tf2_ros tf2_echo rgb_camera_link_frame turtle_chassis`
2. `ros2 run tf2_tools view_frames`  
3. `ros2 run rqt_tf_tree rqt_tf_tree`  
4. `ros2 run tf2_ros tf2_monitor camera_bot_base_link rgb_camera_link_frame`  
5. `ros2 run tf2_ros2_pkg static_broadcaster_front_turtle_frame.py turtle_chassis front_turtle_frame 0.4 0 0.4 0 0.7 3.1416`  
6. `ros2 topic pub /destination_frame std_msgs/msg/String "data: 'front_turtle_frame'"`  
7. `ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=/turtle_cmd_vel`

#### Cam Bot & Turtle

| Initial | After world2cam_bot_base_link | After world2odom |
| --- | --- | --- |
| ![Initial frames](assets/frames_initial.png) | ![After world2cam_bot_base_link](assets/frames_after_world2cam_bot_base_link_tf_pub.png) | ![After world2odom](assets/frames_after_world2odom_static_tf_pub.png) |

#### TF Listener

##### 1. Launching

Terminal 1:  
```
cd ~/ros2_ws
colcon build
source install/setup.bash
ros2 launch tf2_ros2_pkg start_tf_fixes.launch.xml
```  
Terminal 2:  
```
cd ~/ros2_ws
source install/setup.bash
rviz2 -d '~/ros2_ws/src/tf2_ros2_pkg/rviz/unit3_config.rviz'
```  
Terminal 3:
```
cd ~/ros2_ws
source install/setup.bash
ros2 run tf2_ros2_pkg static_broadcaster_front_turtle_frame.py turtle_chassis front_turtle_frame 0.4 0 0.4 0 0.7 3.1416
```  
_**Note:** Can Ctrl-C as this is a one-time publication of a static transform._  

Examine environment:  
```
user:~/ros2_ws$ ros2 service list
/apply_joint_effort
/apply_link_wrench
/box_bot_joint_state/describe_parameters
/box_bot_joint_state/get_parameter_types
/box_bot_joint_state/get_parameters
/box_bot_joint_state/list_parameters
/box_bot_joint_state/set_parameters
/box_bot_joint_state/set_parameters_atomically
/cam_bot/gazebo_ros_state/describe_parameters
/cam_bot/gazebo_ros_state/get_parameter_types
/cam_bot/gazebo_ros_state/get_parameters
/cam_bot/gazebo_ros_state/list_parameters
/cam_bot/gazebo_ros_state/set_parameters
/cam_bot/gazebo_ros_state/set_parameters_atomically
/cam_bot/get_entity_state
/cam_bot/set_entity_state
/cam_bot_force_node/describe_parameters
/cam_bot_force_node/get_parameter_types
/cam_bot_force_node/get_parameters
/cam_bot_force_node/list_parameters
/cam_bot_force_node/set_parameters
/cam_bot_force_node/set_parameters_atomically
/cam_bot_robot_description_publisher/describe_parameters
/cam_bot_robot_description_publisher/get_parameter_types
/cam_bot_robot_description_publisher/get_parameters
/cam_bot_robot_description_publisher/list_parameters
/cam_bot_robot_description_publisher/set_parameters
/cam_bot_robot_description_publisher/set_parameters_atomically
/cam_bot_robot_state_publisher/describe_parameters
/cam_bot_robot_state_publisher/get_parameter_types
/cam_bot_robot_state_publisher/get_parameters
/cam_bot_robot_state_publisher/list_parameters
/cam_bot_robot_state_publisher/set_parameters
/cam_bot_robot_state_publisher/set_parameters_atomically
/camera_controller/describe_parameters
/camera_controller/get_parameter_types
/camera_controller/get_parameters
/camera_controller/list_parameters
/camera_controller/set_parameters
/camera_controller/set_parameters_atomically
/clear_joint_efforts
/clear_link_wrenches
/delete_entity
/differential_drive_controller/describe_parameters
/differential_drive_controller/get_parameter_types
/differential_drive_controller/get_parameters
/differential_drive_controller/list_parameters
/differential_drive_controller/set_parameters
/differential_drive_controller/set_parameters_atomically
/force_move_cam_bot_node/describe_parameters
/force_move_cam_bot_node/get_parameter_types
/force_move_cam_bot_node/get_parameters
/force_move_cam_bot_node/list_parameters
/force_move_cam_bot_node/set_parameters
/force_move_cam_bot_node/set_parameters_atomically
/gazebo/describe_parameters
/gazebo/get_parameter_types
/gazebo/get_parameters
/gazebo/list_parameters
/gazebo/set_parameters
/gazebo/set_parameters_atomically
/gazebo_ros_force/describe_parameters
/gazebo_ros_force/get_parameter_types
/gazebo_ros_force/get_parameters
/gazebo_ros_force/list_parameters
/gazebo_ros_force/set_parameters
/gazebo_ros_force/set_parameters_atomically
/gazebo_ros_p3d/describe_parameters
/gazebo_ros_p3d/get_parameter_types
/gazebo_ros_p3d/get_parameters
/gazebo_ros_p3d/list_parameters
/gazebo_ros_p3d/set_parameters
/gazebo_ros_p3d/set_parameters_atomically
/get_model_list
/odom_to_tf_broadcaster_node/describe_parameters
/odom_to_tf_broadcaster_node/get_parameter_types
/odom_to_tf_broadcaster_node/get_parameters
/odom_to_tf_broadcaster_node/list_parameters
/odom_to_tf_broadcaster_node/set_parameters
/odom_to_tf_broadcaster_node/set_parameters_atomically
/pause_physics
/reset_simulation
/reset_world
/rviz/describe_parameters
/rviz/get_parameter_types
/rviz/get_parameters
/rviz/list_parameters
/rviz/set_parameters
/rviz/set_parameters_atomically
/set_camera_info
/spawn_entity
/static_transform_publisher_turtle_odom/describe_parameters
/static_transform_publisher_turtle_odom/get_parameter_types
/static_transform_publisher_turtle_odom/get_parameters
/static_transform_publisher_turtle_odom/list_parameters
/static_transform_publisher_turtle_odom/set_parameters
/static_transform_publisher_turtle_odom/set_parameters_atomically
/turtle_robot_description_publisher/describe_parameters
/turtle_robot_description_publisher/get_parameter_types
/turtle_robot_description_publisher/get_parameters
/turtle_robot_description_publisher/list_parameters
/turtle_robot_description_publisher/set_parameters
/turtle_robot_description_publisher/set_parameters_atomically
/turtle_robot_state_publisher/describe_parameters
/turtle_robot_state_publisher/get_parameter_types
/turtle_robot_state_publisher/get_parameters
/turtle_robot_state_publisher/list_parameters
/turtle_robot_state_publisher/set_parameters
/turtle_robot_state_publisher/set_parameters_atomically
/unpause_physics

user:~/ros2_ws$ ros2 service list | grep entity_state
/cam_bot/get_entity_state
/cam_bot/set_entity_state

user:~/ros2_ws$ ros2 service type /cam_bot/set_entity_state
gazebo_msgs/srv/SetEntityState

user:~/ros2_ws$ ros2 interface show gazebo_msgs/srv/SetEntityState
gazebo_msgs/EntityState state   # Entity state to set to.
        string name
                                    # An entity can be a model, link, collision, light, etc.
                                    # Be sure to use gazebo scoped naming notation (e.g. [model_name::link_name])
        geometry_msgs/Pose pose
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1
        geometry_msgs/Twist twist
                Vector3  linear
                        float64 x
                        float64 y
                        float64 z
                Vector3  angular
                        float64 x
                        float64 y
                        float64 z
        string reference_frame
                                    # Leaving empty or "world" defaults to inertial world frame.
                                # Be sure to fill all fields, values of zero have meaning.
---
bool success                    # Return true if setting state was successful.

user:~/ros2_ws$ ros2 service type /cam_bot/get_entity_state
gazebo_msgs/srv/GetEntityState

user:~/ros2_ws$ ros2 interface show gazebo_msgs/srv/GetEntityState
string name                          # Entity's scoped name.
                                     # An entity can be a model, link, collision, light, etc.
                                     # Be sure to use gazebo scoped naming notation (e.g. [model_name::link_name])
string reference_frame               # Return pose and twist relative to this entity.
                                     # Leaving empty or "world" will use inertial world frame.
---
std_msgs/Header header               # Standard metadata for higher-level stamped data types.
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id
                                     # * header.stamp Timestamp related to the pose.
                                     # * header.frame_id Filled with the relative_frame.
gazebo_msgs/EntityState state        # Contains pose and twist.
        string name
                                    # An entity can be a model, link, collision, light, etc.
                                    # Be sure to use gazebo scoped naming notation (e.g. [model_name::link_name])
        geometry_msgs/Pose pose
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1
        geometry_msgs/Twist twist
                Vector3  linear
                        float64 x
                        float64 y
                        float64 z
                Vector3  angular
                        float64 x
                        float64 y
                        float64 z
        string reference_frame
                                    # Leaving empty or "world" defaults to inertial world frame.
bool success                         # Return true if get was successful. If false, the state contains garbage.
```
```
user:~/ros2_ws$ ros2 node list
/box_bot_joint_state
/cam_bot/gazebo_ros_state
/cam_bot_force_node
/cam_bot_robot_description_publisher
/cam_bot_robot_state_publisher
/camera_controller
/differential_drive_controller
/force_move_cam_bot_node
/gazebo
/gazebo_ros_force
/gazebo_ros_p3d
/odom_to_tf_broadcaster_node
/rviz
/static_transform_publisher_turtle_odom
/transform_listener_impl_55769f9a66d0
/turtle_robot_description_publisher
/turtle_robot_state_publisher

user:~/ros2_ws$ ros2 node info /cam_bot/gazebo_ros_state
/cam_bot/gazebo_ros_state
  Subscribers:
    /clock: rosgraph_msgs/msg/Clock
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /cam_bot/link_states: gazebo_msgs/msg/LinkStates
    /cam_bot/model_states_demo: gazebo_msgs/msg/ModelStates
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /cam_bot/gazebo_ros_state/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /cam_bot/gazebo_ros_state/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /cam_bot/gazebo_ros_state/get_parameters: rcl_interfaces/srv/GetParameters
    /cam_bot/gazebo_ros_state/list_parameters: rcl_interfaces/srv/ListParameters
    /cam_bot/gazebo_ros_state/set_parameters: rcl_interfaces/srv/SetParameters
    /cam_bot/gazebo_ros_state/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
    /cam_bot/get_entity_state: gazebo_msgs/srv/GetEntityState
    /cam_bot/set_entity_state: gazebo_msgs/srv/SetEntityState
  Service Clients:

  Action Servers:

  Action Clients:

```

#### Unicycle

| Mesh | Spawned | TF in Rviz2 |
| --- | --- | --- |
| ![Mesh](assets/unicycle_mesh.png) | ![Gazebo](assets/unicycle_spawned.png) | ![In Rviz2](assets/unicycle_diff_drive_structure.png) |

| Spawn w/o RSP | Spawn w/ RSP |
| --- | --- |
| ![Without robot_state_publisher](assets/unicycle_frames_spawn_wo_robot_state_pub.png) | ![With robot_state_publisher](assets/unicycle_frames_spawn_w_robot_state_pub.png) |



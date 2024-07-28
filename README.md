### tf2_ros2_pkg

#### Useful command-line tools

1. `ros2 run rqt_tf_tree rqt_tf_tree`  
2. `ros2 run tf2_ros tf2_monitor camera_bot_base_link rgb_camera_link_frame`  
3. `ros2 run tf2_ros2_pkg static_broadcaster_front_turtle_frame.py turtle_chassis front_turtle_frame 0.4 0 0.4 0 0.7 3.1416`  
4. `ros2 topic pub /destination_frame std_msgs/msg/String "data: 'front_turtle_frame'"`  
5. `ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=/turtle_cmd_vel`

#### Unicycle

| Mesh | Spawned | TF in Rviz2 |
| --- | --- | --- |
| ![Mesh](assets/unicycle_mesh.png) | ![Gazebo](assets/unicycle_spawned.png) | ![In Rviz2](assets/unicycle_diff_drive_structure.png) |

| Spawn w/o RSP | Spawn w/ RSP |
| --- | --- |




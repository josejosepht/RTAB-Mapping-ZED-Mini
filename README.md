# RTAB-Mapping-ZED-Mini
Implement Real-Time Appearance-Based Mapping (RTAB Mapping) using ZED Mini camera. Includes April Tag detection, data collection, qualitative analysis, and RTAB Mapping with iPhone app.

The following GitHub repositories were used for the implementation of this project:

April Tags: https://github.com/AprilRobotics/apriltag_ros

RTABMap: https://github.com/introlab/rtabmap_ros

zed ROS wrapper: https://github.com/stereolabs/zed-ros-wrapper

Project implementation:
- zed_rtabmap_example.launch: Changed camera_name to “zedm"
- zed_rtabmap.launch: changed the param file being used to the param file we made.
- zed_rtabmap_db_recorder.launch :
    - The purpose of making this launch file was to be able to record specific relevant topics.
    - Relevant topics were decided upon after analyzing the subscriptions and publications of each ROS node running.
    - The following topics are recorded by the launch file:
      ```
      /tf 
      /tf_static 
      /zedm/global_pose 
      /zedm/goal 
      /zedm/goal_node 
      /zedm/gps/fix 
      /zedm/imu 
      /zedm/initialpose 
      /zedm/republish_node_data 
      /zedm/tag_detections 
      /zedm/user_data_async 
      /zedm/zed_node/depth/depth_registered 
      /zedm/zed_node/rgb/camera_info 
      /zedm/zed_node/rgb/image_rect_color
      ```

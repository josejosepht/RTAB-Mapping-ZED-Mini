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
## Qualitative Analysis of results
![image](https://github.com/josejosepht/RTAB-Mapping-ZED-Mini/assets/97187460/3d64d1fb-918f-43dd-837f-abdc301b0c76)

![image](https://github.com/josejosepht/RTAB-Mapping-ZED-Mini/assets/97187460/4a83cefa-f028-4e4c-829e-486ccd73e84b)

![image](https://github.com/josejosepht/RTAB-Mapping-ZED-Mini/assets/97187460/e98dd349-c4d5-484e-8db9-59716875c2da)

![image](https://github.com/josejosepht/RTAB-Mapping-ZED-Mini/assets/97187460/79246b4b-b994-4414-aa4c-1ba51b80277a)

![image](https://github.com/josejosepht/RTAB-Mapping-ZED-Mini/assets/97187460/7985be06-2e8f-4e35-951c-b5695e5b669d)

The Holy Grail of mapping!!: [iPhone RTABMap App](https://apps.apple.com/lk/app/rtab-map-3d-lidar-scanner/id1564774365)
![image](https://github.com/josejosepht/RTAB-Mapping-ZED-Mini/assets/97187460/44b549d3-71f2-47fc-8f01-39bc1d20556b)




## Conclusions and Future scope
- Glass windows and doors posed a problem as we encountered difficulties with 3D reconstruction using RTAB since the features on the other side of the glass were also detected and registered, leading to imperfect reconstruction.
- The performance of RTAB-Map was impacted by illumination effects. Poor 3D reconstructions are attributed to both excessive and insufficient illumination.
- Future scope: Combine RTAB-SLAM with April tag detection and implement path planning on autonomous platforms.


## References:
- [Concise description of visual slam](https://www.automate.org/blogs/what-is-visual-slam-technology-and-what-is-it-used-for)
- [Breakdown of visual slam implementation in MATLAB](https://www.mathworks.com/help/vision/ug/visual-simultaneous-localization-and-mapping-slam-overview.html)
- [RTABMap tutorials](http://introlab.github.io/rtabmap/)
- [Paper:Comparative assessment of point feature detectors in the context of robot navigation](https://www.researchgate.net/publication/264838423)
- [Stereo lab link for zed mini camera specs](https://www.stereolabs.com/zed-mini/)
- [ROS wiki page for apriltag_ros wrapper](http://wiki.ros.org/apriltag_ros)

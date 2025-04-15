# uav_geometric_control

Geometric control in SE(3) for UAVs.

1. Clone the repository into your ROS workspace:
    ```sh 
    cd ros_ws # Navigate to your ROS workspace
    git clone git@github.com:JakobDomislovic/uav_geometric_control.git
    ```
2. Build the package: 
    ```sh 
    catkin build uav_geometric_control
    source devel/setup.bash
    ```
3. Start the session:
    ```sh 
    roscd uav_geometric_control/startup/geometric_control_sim
    ./start.sh
    ```
4. After takeoff, in tmux, call the service to change the controller:
    ```sh 
    rosservice call /$UAV_NAMESPACE/control_manager/change_controller "input: 'Geometric'"
    ```
5. Test your controller by sending a reference to the tracker:
    ```sh
    rostopic pub /$UAV_NAMESPACE/tracker/input_pose
    ```
6. (Optional) Test your controller by sending a direct reference:
    ```sh
    rostopic pub /$UAV_NAMESPACE/position_hold/trajectory
    ```

## TODO

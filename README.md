# uav_geometric_control

Geometric control in SE(3) for UAV.

1. Clone repo in your ROS workspace.
    ```sh 
    cd ros_ws # position yourself to your ROS workspace
    git clone git@github.com:JakobDomislovic/uav_geometric_control.git
    ```
2. Build package. 
    ```sh 
    catkin build uav_geometric_control
    source devel/setup.bash
    ```
3. Start session.
    ```sh 
    roscd uav_geometric_control/startup/geometric_control_sim
    ./start.sh
    ```
4. After takeoff, in tmux call service to change controller.
    ```sh 
    rosservice call /$UAV_NAMESPACE/control_manager/change_controller "input: 'Geometric'"
    ```
5. Test your controller by giving reference to tracker.
    ```sh
    rostopic pub /$UAV_NAMESPACE/tracker/input_pose
    ```
6. (Optional) Test your controller by giving direct reference.
    ```sh
    rostopic pub /$UAV_NAMESPACE/position_hold/trajectory
    ```

## TODO

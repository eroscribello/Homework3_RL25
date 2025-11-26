# RL2025_Homework3
Clone this repo in your src folder of your ros2 workspace.
then you must build the px4_msgs package, thus run the following command in the ros2 workspace:
```
colcon build --symlink-install --packages-select px4_msgs && source install/setup.bash
```
To run the bridge between ros2 and px4 run this command in the src folder:
```
./DDS_run.sh
```
then, to run the gazebo simulation of our customized drone model, run the following command in the PX4-Autopilot folder
```
make px4_sitl gz_HomeworkDrone
```
To run the force land node you must build the packages, so in ros2 workspace run
```
colcon build --symlink-install --packages-select force_land && source install/setup.bash
```
and once you have run QGRoundControl App outside the docker container and the px4 gazebo simulationa inside of the container, run this command:
```
ros2 run force_land force_land
```
Eventually to generate and track a trajectory you must utilize the offboard_rl package,thus 
```
colcon build --symlink-install --packages-select offboard_rl && source install/setup.bash
```
and run the following command
```
ros2 run offboard_rl traj
```
it will ask you a set of waypoints to follow, to testing use the following set 
```
9
0 0 10 0
10 -10 10 0.1
25 -15 10 0.2
30 -10 10 0.3
25 0 10 0.7
30 10 10 0.3
25 15 10 0.2
10 10 10 0.1
0 0 10 0
30
```

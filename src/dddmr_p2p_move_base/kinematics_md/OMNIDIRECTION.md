## Omni Drive Simulation

This tutorial demonstrate how to bring up a 4 wheel steering robot (run on the omni drive model) and use dddmr_navigation to navigate the robot.

### Bring up zinger 4ws robot.
```
cd ~/dddmr_navigation/src/dddmr_p2p_move_base/simulation/
./zinger_bring_up.bash
```
A simulated 4ws robot will be bring up in a docker container.

### Run Navigation Stack
Open another terminal to run navigation stack (If you already have a dddmr development container, you can ignore this step).
```
cd dddmr_navigation/dddmr_docker/docker_file/
./run_x64.bash
```
You shoule now in the dddmr_x64 container, now compile and then run:
```
cd dddmr_navigation
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
source install/setup.bash
ros2 launch p2p_move_base zinger_localization.launch
```
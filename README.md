Установка

```shell
git clone git@github.com:rirpc-uav-lab/px4_simulator_ws.git
cd simulator_ws
vcs import < ssh.repos
colcon build
echo source $(pwd)/install/setup.bash >> ~/.bashrc
echo "export GZ_SIM_RESOURCE_PATH=$(pwd)/src/models_and_worlds/worlds:$(pwd)/src/models_and_worlds/models:\${GZ_SIM_RESOURCE_PATH}" >> ~/.bashrc
source ~/.bashrc
```

## Установка

1. Установить ROS2 Humble.
2. Внесем изменения в bash:
```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
3. Установить и подготовить репозиторий

```shell
git clone git@github.com:rirpc-uav-lab/px4_simulator_ws.git
cd px4_simulator_ws
vcs import < ssh.repos
colcon build
echo source $(pwd)/install/setup.bash >> ~/.bashrc
echo "export GZ_SIM_RESOURCE_PATH=$(pwd)/src/px4_models_and_worlds/worlds:$(pwd)/src/px4_models_and_worlds/models:\${GZ_SIM_RESOURCE_PATH}" >> ~/.bashrc
source ~/.bashrc
```

4. Сделать обновление ссылок и обновление пакетов ОС с помощью команд:
```bash
sudo apt update
sudo apt upgrade
```
5. Установить пакет setuptools. 
```bash
pip3 install setuptools==58.2.0
```
6. Установить [Gazebo Garden](https://gazebosim.org/docs/garden/install_ubuntu).
7. Установить mavros:
```bash
sudo apt install ros-humble-mavros
sudo apt install ros-humble-mavros-extras
```
8. Установить GeographicLib
```bash
sudo wget https://raw.githubusercontent.com/mavlink/mavros/ros2/mavros/scripts/install_geographiclib_datasets.sh

sudo bash install_geographiclib_datasets.sh

exit
```
9. Установить репизиторий ros_gz
```bash
sudo sh -c 'echo "deb [arch=$(dpkg --print-architecture)] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" > /etc/apt/sources.list.d/ros2-latest.list'

curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

sudo apt-get update

sudo apt install ros-humble-ros-gzgarden
```
10. Установить автопилот:
```bash
cd
git clone git@github.com:rirpc-uav-lab/PX4-Autopilot.git --recursive
bash ./PX4-Autopilot/Tools/setup/ubuntu.sh --no-sim-tools
```
После этого **обязательно** перезапускаем компьютер, далее прописываем
```bash
cd PX4-Autopilot/
make px4_sitl
```
**Перезапускаем терминал и можно запускать симулятор.**



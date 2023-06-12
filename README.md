# Crazyswarm with Webots Simulation
Author: Joshua Julian Damanik

## Installation

- Install ROS2 Humble: https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html
- Clone this repository
    ```bash
    git clone --recursive https://github.com/joshuadamanik/crazyswarm-ros.git
    ```
- Install crazyswarm2 dependencies
    ```bash
    sudo apt install python3-pip libboost-program-options-dev libusb-1.0-0-dev
    pip3 install rowan
    pip3 install cflib transforms3d
    sudo apt-get install ros-humble-tf-transformations
    ```
- Build the crazyflie-firmware
    ```bash
    sudo apt-get install make gcc-arm-none-eabi
    cd crazyflie-firmware
    make cf2_defconfig
    make -j 12
    make cf2_defconfig
    make bindings_python
    ```
- Export Python path to include firmware/build folder
    ```bash
    export PYTHONPATH=<replace-with-path-to>/crazyflie-firmware/build:$PYTHONPATH
    ```
- Build the package
    ```bash
    source /opt/ros/humble/setup.bash
    cd ../ros2_ws
    colcon build --symlink-install
    ```

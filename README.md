# Carla_Project

### Step 1 - Begin Installation by following the instructions mentioned [here](https://carla.readthedocs.io/en/latest/start_quickstart/).

Exact commands that were used are as follows:

    $ pip install pygame numpy
    $ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 1AF1527DE64CB8D9
    $ sudo add-apt-repository "deb [arch=amd64] http://dist.carla.org/carla $(lsb_release -sc) main"
    $ sudo apt-get update
    $ sudo apt-get install carla-simulator
    $ cd /opt/carla-simulator 
    $ ./ImportAssets.sh

To launch the Simulation ,due to some driver issue on NVIDIA GTX950M, Instead of 

    $ ./CarlaUE4.sh

try,

    $ ./CarlaUE4.sh -opengl


The reason for this can be found [here](https://carla.readthedocs.io/en/latest/adv_rendering_options/)

Run this to launch in low graphics mode:

    $ ./CarlaUE4.sh -opengl -quality-level=Low

### Step 2 - Setup NVIDIA Drivers to work on your Linux system, which can improve the Graphics of the Carla Visualizations.

To do this, do the following steps:

    Software & Updates > Additional Drivers > Select the latest under NVIDIA

### Step 3 - Download Anaconda

The latest Carla version requires Python 3.7. Download Anaconda and setup a Virtual Environment.

Steps to download Anaconda can be found [here](https://docs.anaconda.com/anaconda/install/linux/).

### Step 5 - Verify all python installations

Do this by shifting to **/opt/carla-simulator/PythonAPI/examples** directory and trying out the Python Example Scripts

### Step 6 - Setting up Ros bridge

Visit the [link](https://carla.readthedocs.io/en/latest/ros_installation/) to setup ROS bridge.

This is what worked for me:

Python 2.7 + ROS Melodic + For Ubuntu 18.04 (Bionic)

Create a new Conda environment with Python 2.7

    $ conda create -n py2env python=2.7

    $ conda activate py2env

    $ pip install pygame

    $ pip install pyyaml

    $ pip install rospkg

    $ pip2 install opencv-python==4.2.0.32

When done, do the following:

    $ source /opt/carla-ros-bridge/melodic/setup.bash

    $ export PYTHONPATH=$PYTHONPATH:/opt/carla-simulator/PythonAPI/carla/dist/carla-0.9.11-py2.7-linux-x86_64.egg

Test ROS Bridge launch file

    $ roslaunch carla_ros_bridge carla_ros_bridge.launch





### Important Carla Commands

 - To launch Carla with a window

        $ ./CarlaUE4.sh -opengl -quality-level=Low

 - To launch Carla without a window
 
        $ DISPLAY= ./CarlaUE4.sh -opengl


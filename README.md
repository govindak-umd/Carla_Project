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

### Step 3 - Verify the Python Version. Latest Carla requires Python 3.7.

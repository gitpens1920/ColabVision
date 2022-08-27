# Installing CARLA on server

Verify that the system has adequate space and capabiliites:\
https://carla.readthedocs.io/en/latest/build_faq/#expected-disk-space-to-build-carla

Short answer
- 170GB free drive space
- 8GB GPU

Basic steps:
1. Install CARLA packages on server

> This requires ~17GB of space and ultimately will be very RAM intensive when running. A micro server will download and install it, but will not be able to run the SW without significant lag.
> start byobu, split screen run htop in lower screen to see usage (just for kicks)

2. Install the remote server packages

## Install CARLA 

### Install SW pre-reqs 

Carla requires an UNREAL engine to run. Follow the installation steps here or it will be a very painful process to troubleshoot...
https://carla.readthedocs.io/en/latest/build_linux/#software-requirements

### Install the CARLA packages
Follow the instruction here

https://carla.readthedocs.io/en/latest/start_quickstart/#a-debian-carla-installation

### Notes:

## Install Rlib for remote server 

Follow the instruction here

https://carla.readthedocs.io/en/latest/tuto_G_rllib_integration/#running-on-aws

### Notes:


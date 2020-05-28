# SWASH using Docker
Docker installation of SWASH. The package is running  `Ubuntu 18.04` under the hood. The exetutable can be used in all operating systems without any further modifications.

The **SWASH** model is available in: http://swash.sourceforge.net.
This code is merely intended to help with the installation of the
package through Docker. The methods, physics and description of the model
should be sought in the link about and references therein.

Download and install Docker before runnning this script:
https://docs.docker.com/get-docker/

The `swashstart` bash script is all that is required to run **SWASH**.

### Usage:

Clone the repository in a local folder (here called swash)
```
cd ~/
git clone https://github.com/ikarmpadakis/swash.git ./swash
cd swash
```
Initialise **SWASH**. This creates a new data folder in `~/swash_data`. This folder mounted in the container and will contain all the simulated data. The location of the fodler can be modified by changing the `mnt` variable. The container is destroyed after exiting so it does not leave any traces in the local system. 
```
./swashstart
```
The `swashstart` command starts a new terminal inside the ubuntu container where swash is installed. Now swash can be run as if it was installed locally on the PC. 
One of the example files from the SWASH team (see references above) is copied over in the data folder.
```
cd Example/a11stwav/
swashrun -input a11stw01
```
In this respect `swashrun` works in the wame way as in a linux system (see SWASH Manual)

While the swash image will run on all platforms the swashstart bash script might not (has not been written with WIndows in mind, because SWASH already has an installer. Adjusting the folder creation to be Windows compatible will come soon.

*Tested on MacOS and Ubuntu*

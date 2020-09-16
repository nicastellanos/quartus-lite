# ECED 4260 Install instructions

Before getting started Ensure you have the latest version of [XQuartz](https://www.xquartz.org) and [Docker Desktop](https://www.docker.com/get-started) installed.

Note this docker container will work for simulation enviroments. It is much lighter than a VM (~20GB vs 50GB) but will not support USB passthrough. If working with hardware, you will need a VM (and a lot more memory) information for setting up quartus using a VM can be found [here](https://siytek.com/quartus-mac-virtualbox-ubuntu/)


## XQuartz

Open XQuartz and go into the XQuartz>Preferences found in the top lefthand corner of the screen. Once in preferences go to Security and click **Allow Connections from Network Clients**

Restart the application to set the preferences.

**Note:** I found I had to resart my computer so the XQuartz settings took in effect



## Docker Setup and Build

Copy this repository through download or git clone

Within your terminal go to directory where this repo is stored.

'cd ~/path/to/repo/quartus-lite/'

 Open docker and confirm its functionality by running

`docker --help`

If docker is running correctly you will get the help text prompt on the terminal. Once confirming docker is running you will begin by running

`docker build -t 'eced4260:latest' .`

You should expect to see the docker build operation begin, it will build the OS and download the necessary software for Quartus Prime Lite. This will take some time since the install is quite large.

Once the build has successfully completed we can begin running the setup script to run the docker container

While in the repositorys directory you want to allow the quartus.sh script permission to run. This can be done by

`chmod +x quartus.sh`

## Running the container

Now we are ready to run the container

Once again move into the working directory of this download where the quartus.sh file is stored. Check docker is running then in the terminal enter

`./quartus /bin/bash`

The docker contrainer should execute and you should see your user change to root as you are now "inside" the container.

Finally run `quartus` to run the Quartus Prime Lite Program you should see the program begin running

**Note:** If the quartus command is not working you can find the executable in /opt/intelFPGA_lite/20.1/quartus/bin and run './quartus' in the terminal




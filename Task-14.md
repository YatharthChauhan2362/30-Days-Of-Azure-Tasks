# 1. Mount a volume/ directory from the host system to a Docker container

Here are the general steps to mount a volume/directory from the host system to a Docker container in Azure:
1.	Log in to the Azure portal (portal.azure.com)
2.	Select "Virtual machines" from the left-hand navigation menu
3.	Select the virtual machine that is running the container
4.	Select "Disks" from the left-hand navigation menu
5.	Select the disk that you want to use as the volume
6.	Select "Attach" from the top menu
7.	Select the container that you want to mount the volume to
8.	In the command line of the container, use the docker run command to launch the container with the -v option to specify the host path and the container path for the volume.

For example, if you want to mount the '/data' directory on the host to '/app/data' in the container, you would use the following command:

    docker run -v /data:/app/data <image-name>

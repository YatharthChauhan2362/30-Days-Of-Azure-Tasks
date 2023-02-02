# 1. Launch a Linux VM and Install Docker services on that VM.

Here are the general steps to launch a Linux VM and install Docker services on that VM using the Azure portal:

1.	Go to the Azure portal (https://portal.azure.com/) and create a new Linux VM by clicking on "Create a resource" -> "Compute" -> "Virtual Machine"

2.	Fill in the required information for the VM, such as name, resource group, and image. You can select a Linux distro of your choice.

3.	Select the "Size" and "Storage" as per your requirement.

4.	Under "Networking" configure the network settings as per your requirement.

5.	Click on "Review + Create" to review the settings and then click on "Create" to launch the VM.

6.	Once the VM is created, go to the "Overview" page of the VM and click on "Connect" to establish a connection to the VM using SSH.

7.	Once you are connected to the VM, you can install Docker by following the instructions for your specific Linux distribution.

8.	For Ubuntu, you can install Docker by running the following commands:

    sudo apt-get update
    sudo apt-get install -y docker.io
    sudo systemctl start docker
    sudo systemctl enable docker
    
9.	You can verify the installation by running the command:

    docker --version

10.	Once the installation is done, you can start using the Docker service on your Linux VM.

### Tutorial Link:

- []()


# 2. Launch a Docker container and set up an Apache/ Nginx server over that container.

Here are the general steps to launch a Docker container and set up an Apache/Nginx server over that container in Azure:
1.	Log in to the Azure portal (portal.azure.com)
2.	Select "Containers" from the left-hand navigation menu
3.	Select "Create a container" from the top menu
4.	Select the container registry that you want to use to pull the image
5.	Select the image of the web server (Apache or Nginx) that you want to use
6.	Configure the container settings as desired (e.g. container name, CPU, memory, ports)
7.	Select "Create" to launch the container
8.	After the container is running, you can use the docker exec command to enter the container and configure the web server

For example, if you are using Apache, you can use the following command to enter the container:

    docker exec -it <container-name> /bin/bash

Then you can use the following command to configure Apache:

    apt-get update
    apt-get install apache2




# 3. Create a simple HTML page to launch over the web server.

Here are the general steps to create a simple HTML page to launch over the web server running on a Docker container:

1.	Establish a connection to the Linux VM where the Docker container is running. You can do this by using the "Connect" button on the Azure portal, or by using an SSH client such as PuTTY.

2.	Navigate to the directory where the web server files are stored. For Apache, this is typically in the **/usr/local/apache2/htdocs** directory. For Nginx, this is typically in the **/usr/share/nginx/html** directory.

3.	Create a new file in the directory with the name index.html or any other name as per your requirement.

4.	Open the file using a text editor and add the following basic HTML code:

    <!DOCTYPE html>
    <html>
    <head>
        <title>30 Days of Azure Tasks</title>
    </head>
    <body>
        <h1>Welcome to my 30 Days Azure Tasks with Yatharth Chauhan</h1>
    </body>
    </html>

5. Save the file and exit the text editor.

6. You can now access the web page by using the public IP address of the Linux VM in a web browser.

To launch this HTML page on an Azure web server, you will need to first create a web app in Azure and then deploy your HTML code to it. You can use Azure App Service to create a web app and deploy your HTML code using Git, FTP, or other deployment options. Once your HTML code is deployed, you can access it by visiting the URL of your web app in a web browser.

# 4. Configure the Docker container such that when we start the VM, the Docker Services are up and running and the container is launched automatically such that the web server is turned to active status to reflect the web page just after Starting VM.

Here are the steps you can take to configure a Docker container on an Azure VM such that the container is launched automatically when the VM starts:
1.	Create an Azure VM and install Docker on it.
2.	Create a Dockerfile which will contain all the necessary instructions to build an image of your container.
3.	Build the image from the Dockerfile, this will create a container image.
4.	Use the 

    
    docker run 
    
To start the container and specify the **--restart** flag as **always** to ensure the container automatically restarts when the VM starts.

Example:

    #css
    docker run -d --restart always --name mycontainer -p 80:80 myimage

5. To make sure the container is launched automatically after the VM starts, you can configure the Docker service to start automatically on boot by modifying the **/etc/systemd/system/docker**.service file and adding the **--restart-always** flag to the **ExecStart** line.

    #javascript
    ExecStart=/usr/bin/dockerd --restart-always -H fd://

6. After that, reload the systemctl daemon and enable the docker service to run at the startup

    #bash
    systemctl daemon-reload
    systemctl enable docker

Once you have completed these steps, the Docker container should be launched automatically whenever the VM is started, and the web server inside the container should be active and ready to serve the HTML page.


# 5. Perform the same task using Docker File

Here are the steps you can take to configure a Docker container on an Azure VM using a Dockerfile:

1.	Create an Azure VM and install Docker on it.
2.	Create a new file named Dockerfile in your project directory.
3.	In the Dockerfile, specify the base image you want to use for the container, and any additional instructions for installing dependencies or configuring the container.

Example:

    #sql
    FROM nginx:latest
    COPY . /usr/share/nginx/html

This will use the latest version of nginx as the base image and copy all the files in the current directory to the container's **/usr/share/nginx/html** directory.

4. Build the image from the Dockerfile by running the following command:

    docker build -t myimage .

This command will create an image called myimage using the instructions in the Dockerfile.

Use the 

    docker run 
    
To start the container and specify the **--restart** flag as **always** to ensure the container automatically restarts when the VM starts.

Example:

    #css
    docker run -d --restart always --name mycontainer -p 80:80 myimage

6. To make sure the container is launched automatically after the VM starts, you can configure the Docker service to start automatically on boot.

You can do this by creating a systemd service unit file for the container, which tells systemd to start the container when the system boots.

Example:

    #makefile

    [Unit]
    Description=My Docker Container

    [Service]
    Restart=always
    ExecStart=/usr/bin/docker start -a mycontainer
    ExecStop=/usr/bin/docker stop -t 2 mycontainer

    [Install]
    WantedBy=multi-user.target

7. After creating the service unit file, you can reload the systemd daemon and enable the service.

    #bash
    systemctl daemon-reload
    systemctl enable mycontainer.service

Once you have completed these steps, the Docker container should be launched automatically whenever the VM is started, and the web server inside the container should be active and ready to serve the HTML page.
# 1. Create a sample .NET application and host it on Azure App Services.

Here are the general steps to create a sample .NET application and host it on Azure App Services using the Azure portal:

1.	Install the latest version of Visual Studio on your computer.

2.	In Visual Studio, create a new project by clicking on "File" -> "New" -> "Project"

3.	Select "ASP.NET Web Application" and provide a name for your project. Select the framework you want to use (e.g. .NET Core) and click "Create"

4.	In the next window, select "Web Application (Model-View-Controller)" template and click "Create"

5.	Once the project is created, you can add new controllers, views and models as per your requirement

6.	Build your application by going to "Build" -> "Build Solution"

7.	Go to the Azure portal (https://portal.azure.com/) and create a new Azure App Service by clicking on "Create a resource" -> "Web" -> "Web App"

8.	Fill in the required information for the App Service, such as name, resource group, and operating system

9.	Under "Deployment options" select "Code" and configure the deployment options as per your requirement.

10.	Click on "Create" to create the App Service

11.	Once the App Service is created, go to the "Deployment Center" in the App Service blade, and select the deployment option that you have selected.

12.	Follow the instructions to deploy your application to the App Service

### Tutorial Link:

- [How to deploy.Net Core Web Application to Azure App Services](https://youtu.be/811s_WccyH4)


# 2. Create an application gateway and access Azure App service through Azure Application gateway.

Here are the general steps to create an application gateway and access an Azure App Service through it using the Azure portal:

1.	Go to the Azure portal (https://portal.azure.com/) and create a new application gateway by clicking on "Create a resource" -> "Networking" -> "Application Gateway"

2.	Fill in the required information for the application gateway, such as name, resource group, and virtual network.

3.	Select the "Size" and "SKU" as per your requirement.

4.	Under "Backend pools" add your Azure App Service as a backend target.

5.	Under "Listeners" create a new listener with the required protocol and port.

6.	Under "Rules" create a new rule that maps the listener to the backend pool.

7.	Click on "Create" to create the application gateway.

8.	Once the application gateway is created, go to the "Overview" page of the application gateway and copy the public IP address or FQDN.

9.	Update the DNS settings or CNAME records to point to the public IP address or FQDN of the application gateway.

10.	Now you can access your Azure App Service through the application gateway by using the public IP address or FQDN in the browser.

### Tutorial Link:

- [Configuring Application Gateway](https://youtu.be/bPyH0W5oDT8)


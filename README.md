# MyOrchardCoreCMSonLinuxUsingVSCode

Developing Orchard Core CMS Applications on Linux using VS Code 

## YouTube Video

[![OrchardSkillsYouTubeThumbNailLinux](https://user-images.githubusercontent.com/58791170/75269015-80cf7c80-57b5-11ea-9546-a92acc201fea.png)](https://youtu.be/EySZCCwSZ9s)


## PDF Version of the Documentation

[Developing-Orchard-Core-CMS-Applications-on-Linux-Using-VSCode.pdf](https://github.com/orchardcmsnet/MyOrchardCoreCMSonLinuxUsingVSCode/files/4003148/Developing-Orchard-Core-CMS-Applications-on-Linux-Using-VSCode.pdf)

# Developing Orchard Core CMS Applications on Linux Using VS Code

![Microsoft-loves-Linux](https://user-images.githubusercontent.com/58791170/71485130-ccbd6f80-27cc-11ea-8cd5-a5e3490576e6.jpg)

## Introduction

Another option when developing Orchard Core application is to use Linux and VS Code. VS Code is a lightweight IDE (Integrated Development Environment). It’s also a cross platform IDE running on Linux, macOS, and Windows. It has all the popular features of an IDE like intellisence, debugging, built-in Git and most importantly extensions.

## Install VS Code

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-005](https://user-images.githubusercontent.com/58791170/71485113-caf3ac00-27cc-11ea-9655-b684db12ef18.png)

Browse to the URL: 
https://code.visualstudio.com/download
Click on “.deb Debian Ubuntu” button to download the package.
Switch to the Downloads directory.

```
cd ~/Downloads
```

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-006](https://user-images.githubusercontent.com/58791170/71485114-caf3ac00-27cc-11ea-9d17-959595b4856f.png)

Run the command:

```
sudo dpkg -i code_1.41.1-1576681836_amd64.deb

```

## Browse to Debian 10 Package Manager - Install .NET Core

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-007](https://user-images.githubusercontent.com/58791170/71485115-caf3ac00-27cc-11ea-97dc-d4e9842231f9.png)

Browse to the web page Debian 10 Package Manager - Install .NET Core at:

[Debian 10 Package Manager - Install .NET Core](https://docs.microsoft.com/en-us/dotnet/core/install/linux-package-manager-debian10)

## Register Microsoft key and feed

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-001](https://user-images.githubusercontent.com/58791170/71485109-ca5b1580-27cc-11ea-8144-52fabe9c8c76.png)

Run the commands:

```
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## Install the .NET Core SDK

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-002](https://user-images.githubusercontent.com/58791170/71485110-ca5b1580-27cc-11ea-8122-e29add3ca293.png)

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-003](https://user-images.githubusercontent.com/58791170/71485111-ca5b1580-27cc-11ea-85f8-56301143fc22.png)

Note: After installing the .NET SDK, it seems it’s not necessary to install the runtimes.

Run the commands:

```
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.0
```

## Install the ASP.NET Core runtime

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-004](https://user-images.githubusercontent.com/58791170/71485112-ca5b1580-27cc-11ea-921b-56e2d008e575.png)

Run the commands

```
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.0
```

## Install the .NET Core runtime

Run the commands

```
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.0
```

## Code Generation Templates

Orchard Core Templates uses dotnet new template configurations for creating new websites, themes and modules from the command shell.
More information about dotnet new can be found at:

[dotnet new template configurations](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-new)

## Install Orchard Core Code Generation Templates

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-008](https://user-images.githubusercontent.com/58791170/71485116-cb8c4280-27cc-11ea-9e5b-84b644e65df5.png)

Run the command:

```
dotnet new -i OrchardCore.ProjectTemplates::1.0.0-rc1-*
```

## Set NuGet Source to Latest Dev Branch of Orchard Core

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-009](https://user-images.githubusercontent.com/58791170/71485117-cb8c4280-27cc-11ea-9967-147c24bf55b4.png)

This will use the most stable release of Orchard Core. In order to use the latest dev branch of Orchard Core, the following command can be used:

```
dotnet new -i OrchardCore.ProjectTemplates::1.0.0-rc1-* --nuget-source https://www.myget.org/F/orchardcore-preview/api/v3/index.json
```

Once the .NET Core SDK has been installed, the templates can be used for creating Orchard Core web applications

## Create a new Orchard Core CMS Web App

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-010](https://user-images.githubusercontent.com/58791170/71485118-cb8c4280-27cc-11ea-818b-070687cad261.png)

Switch to your projects folder. Mine is located at ~/Documents/GitHub

```
cd ~/Documents/GitHub
```

Run the commands:

```
mkdir MyOrchardCoreCMS
cd MyOrchardCoreCMS/
dotnet new occms -lo none
code .
```

## Create a NuGet.config File

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-011](https://user-images.githubusercontent.com/58791170/71485119-cb8c4280-27cc-11ea-8fea-df71c0a7b080.png)

Click the plus file icon on MYORCHARDCORECMS folder to create a new file.

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-012](https://user-images.githubusercontent.com/58791170/71485120-cb8c4280-27cc-11ea-9884-3033d52b955f.png)

Paste in the contents for the NuGet.config file.
NuGet.config:

```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <packageSources>
        <add key="Orchard Core Preview Feed" value="https://www.myget.org/F/orchardcore-preview/api/v3/index.json" />
    </packageSources>
</configuration>
```

## Create Build Configuration and Run the Orchard Core CMS Web App

Click on the Debug icon.

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-013](https://user-images.githubusercontent.com/58791170/71485121-cb8c4280-27cc-11ea-9cb0-335032fde749.png)

Click the "create a launch.json file".

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-014](https://user-images.githubusercontent.com/58791170/71485122-cb8c4280-27cc-11ea-983e-1340866b7d4b.png)

Select .Net Core

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-015](https://user-images.githubusercontent.com/58791170/71485124-cc24d900-27cc-11ea-8951-d69c3ac2a62a.png)

Click on the green triangle to start running the application.

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-016](https://user-images.githubusercontent.com/58791170/71485125-cc24d900-27cc-11ea-81b6-3e46e4817f26.png)

Application is running.

## Launch Web Browser

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-017](https://user-images.githubusercontent.com/58791170/71485126-cc24d900-27cc-11ea-86d2-bf3e5fc54198.png)

Launch the web browser and set the URL to:

[http://localhost:5000/](http://localhost:5000/)

Congratulations Our Orchard Core Application is running on Linux.  Enter the site name, Blog for the Recipe, your Default Time Zone, Sqlite for the database and then your administrator credentials.

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-018](https://user-images.githubusercontent.com/58791170/71485127-cc24d900-27cc-11ea-8844-c14ddb00cca7.png)

Now browse to the dashboard at:

[http://localhost:5000/admin](http://localhost:5000/admin)

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-019](https://user-images.githubusercontent.com/58791170/71485128-ccbd6f80-27cc-11ea-8f28-2647723f5301.png)

Login with your admin credentials.

![Developing-Orchard-Core-CMS-Applications-Using-Linux-and-VSCode-020](https://user-images.githubusercontent.com/58791170/71485129-ccbd6f80-27cc-11ea-972c-7a59201dd157.png)

## Conclusion

With ASP.NET and Orchard Core CMS you can setup the development environment and create an application in minutes on Linux, macOS, or Windows machine using VS Code. Best of all it’s all free.

## GitHub

The complete source code is located [here](https://github.com/orchardcmsnet/MyOrchardCoreCMSonLinuxUsingVSCode).

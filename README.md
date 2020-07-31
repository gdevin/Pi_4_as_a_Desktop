# Pi 4 as a Desktop

This document is an outline of setup steps to configure a Raspberry Pi 4 as a desktop.  The primary focus of these steps is for a system with the following applications and service tasks.

* Video conferencing, primarily MS Teams but also Zoom
* Microsoft 365, including Exchange Online
* CA Service Desk Manager and Banner Self-Service Applications
* Remote access, RDP (Remmina), and VPN (OpenConnect)
* Script and code editing with Visual Studio Code
* Version control with Git
* Azure management with PowerShell Core

There are several operating system options for the Raspberry Pi, but Ubuntu-Mate had the most hardware optimizations at the time of this testing.  Version 20.04 located here, https://ubuntu-mate.org/download/arm64/, is what I used.

Here is a list of the hardware.
* 8GB Pi 4
* Ice Tower cooler
* Samsung EVO Plus SD Card
* Corsair Voyager premium flash drive
* 5 amp power supply
* 2.4 GHz wireless keyboard and mouse
* Jabra external USB headset
* Microsoft LifeCam
* External speaker with 3.5mm audio jack
* USB extension cable

I will leave the details about installing the OS and getting all the devices working for another document.  However, I will mention that the USB extension cable is a must if you are going to use a wireless keyboard and mouse.  I tested two different units, and both caused interference for the keyboard and mouse.

The following GitHub repository will install Microsoft Teams, https://github.com/gdevin/Teams.  This installation expects there to be a Chromium profile located in the following directory, "~/snap/chromium/common/chromium/Profile 1". 

The Chromium "Profile 1" can also be used to access Microsoft 365, and the service desk/banner applications.

Follow the "via Git clone" section here to install custom prompt for Git in bash, https://github.com/magicmonty/bash-git-prompt.

Use the website for details about installing Visual Studio Code, https://code.headmelted.com/.  Do not forget to run sudo -s!

Powershell Core has not officially been released for Ubuntu 20.04, see https://github.com/PowerShell/PowerShell.  However, I was able to use the build for Raspbian and get it to work.  Here are the steps.

################################### 
# Download and extract PowerShell 
# Grab the latest tar.gz 
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-arm32.tar.gz 
# Make folder to put powershell 
mkdir ~/powershell 
# Unpack the tar.gz file 
tar -xvf ./powershell-7.0.3-linux-arm32.tar.gz -C ~/powershell 
# Start PowerShell 
~/powershell/pwsh

Here is a tutorial on using pwsh, https://matthewdavis111.com/powershell/manage-azure-ad-powershell-core/.




# *How to Install Android app from .apk file on Chromebook without Developer mode*
---

## Install Crostini (official Linux environment)
You can install it just by turning it on from the ChromeOS settings.  
> Settings > **Advanced** > **Developers**
>> Next to **Linux develop environment**, select **Turn On**

## Install ADB
Install the ADB used to install the app from the .apk file.  
First, update the package.  
``` sudo apt update && sudo apt upgrade ```  
Install the ADB.  
``` sudo apt install adb ```  

## Enable ADB debugging
Change the settings for connecting to the Android container in the ChromeOS with ADB.  
> Settings > **Advanced** > **Developers** > **Linux develop environment**
>>Next to "**Android app Development**", enable **Enable ADB debugging**
### *Once enabled,Powerwash is required to disable it*

## ADB connection to Android container
ADB connect to the Android container to install the .apk file.  
Start a terminal and execute the command.  
``` adb connect 100.115.92.2:5555 ```  
You can check the terminal currently connected to ADB with ` adb devices `.  
` 100.115.92.2:5555    device ` is an Android container.  

## Install Android app from .apk file
Now that you are ready, install the .apk file.  
The installation command using ADB is as follows.  
``` adb -s 100.115.92.2:5555 install [.apk file path] ```  
` Success ` is displayed, the installation is complete.  

## Important Point
The following sentence will be displayed on the login screen.  
> *This device may have installed an app that Google has not verified*

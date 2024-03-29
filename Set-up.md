# Set-Up 
## Background
We are using the Nordic nRF52840-Dongle 2.4GHz RF Development Board. To start our initial testing, we simpy want to get your workspace up and running. We are going to be using VSCode, Nordic's provided SDK, and the NRF-Connect Applications. If you are unfamiliar with this line of work, then we will provide some background here:

This is not like an arduino. There is no provided IDE, nor an easy way to 'validate' or 'upload' code. You have to manange storage, and the interfaces between sensors and the device are manually managed, unlike the Arduino which has a serial plotter and other tools built in. 

In order to start using the device, Nordic provides a couple helpful things. 
First of all, they give you an SDK (Software Development Kit) that gives examples on how to use the dongle, provides extremely helpful functions to utilize the device, and lots of documentation. There is a LOT in the SDK, so you don't need to master every part of it, but it is important to know what it is and its general outline. 
Nordic also provides an application called nRF-Connect which contains a number of tools. These tools are used to perform diagnostics for the various components (Bluetooth, RSSI, etc...) and to upload code, manage storage and more.

Those are the basics you ought to know before starting to work with this dongle. 

## Downloads
In order to follow along, you are going to need two things:

1) The SDK
2) nRF-Connect

The SDK is pretty big. I would provide it in this repo, but its too big for Github (without lfs). So for everything that is to come we are using the nRF5 SDK v.16.0.0. This was the latest version as of 5/4/2020. Yu can download this version or a newer version [here](https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK).

Make a file on your computer and put the SDK there, we will go through it later.

You can download nRF-Connect from [here](https://www.nordicsemi.com/Software-and-tools/Development-Tools/nRF-Connect-for-desktop).

## IDE
We are going to be using Visual Studio Code, also known as VS Code. You can get it [here](https://code.visualstudio.com/).
More importantly we are using a C/C++ language support extension by Microsoft. You should be able to find it by simply looking up C/C++ in VS Code, It should be the first option. Just in case, its formal name is ms-vscode.cpptools by Microsoft, and can be found [here](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools).

## ToolChain
There are four options for toolchains provided by Nordic (alongside a couple other minor options like CMSIS):

1) ARM: MDK-ARM
2) GCC: GCC-ARM
3) IAR
4) SES

Now IAR (IAR Workbench) and SES are closed systems. It is very common for people to use SES(Segger Embedded Studio), but I really like VS Code, which is a general-use IDE. Because of this we are going to be using GCC-ARM toolchain. 

So, you might find that you need to connect the SDK to the GNU install folder. You will be able to do this in the maker-file.

To do this navigate to ".\components\toolchain\gcc\Makefile.windows" where you will need to identify where the bin file is for the GCC compiler. In my case it is found here "C:/Program Files (x86)/GNU Tools ARM Embedded/8 2019-q3-update/bin/". You will also need to specify the version you are using and the prefix. In our case, the pre-fix is "arm-none-eabi".

There will be more set-up later once we start an example project, but it will presented when we get there.



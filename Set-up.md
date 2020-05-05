# Set-Up 
## Background
We are using the Nordic nRF52840-Dongle 2.4GHz RF Development Board. To start our initial testing, we simpy want to get your workspace up and running. We are going to be using VSCode, Nordic's provided SDK, and the NRF-Connect Applications. If you are unfamiliar with this line of work, then we will provide some background here:

This is not like an arduino. There is no provided IDE, nor an easy way to 'validate' or 'upload' code. You have to manange storage, and the interfaces between sensors and the device are manually managed, unlike the Arduino which has a serial plotter and other tools built in. 

In order to start using the device, Nordic provides a couple helpful things. 
First of all, they give use an SDK (Software Development Kit) that gives examples on how to use the dongle, provides extremely helpful functions to utilize the device, and lots of documentation. There is a LOT in the SDK, so you don't need to master every part of it, but it is important to know what it is and its general outline. 
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
So you will find the config files for setting up your toolchain in the components folder of the SDK. There are a bunch of different options for your toolchain. The most important desicion is what compiler you will use. For our development we are using the standard GCC toolchain. The compiler is probabably already installed on your machine, but if not you can install it from [here](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm). 

You will then need to set up the maker-file that defines the behaviour of the 'make' command which we will be using to compile our code. To do this navigate to ".\components\toolchain\gcc\Makefile.windows" where you will need to identify where the bin file is for your compiler. In my case it is found here "C:/Program Files (x86)/GNU Tools ARM Embedded/8 2019-q3-update/bin/". You will also need to specify the version you are using and the prefix, which in our case is "arm-none-eabi".



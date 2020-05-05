# SDK
## What is in it?
### &nbsp;Components
&nbsp; <p>This section of the SDK contains different APIs, libraries, and functions to use the differnt capabilities of the dongle. There are also the different toolchains for specific softdevices and their APIs. Finally it contains linker files and other files for connecting the SDK to a given toolchain. We wont go through it all, but will go through some important parts of it:</p>
#### &nbsp;&nbsp;802_15_4
&nbsp;&nbsp;IEEE 802.15.4 is a technical standard which defines the operation of low-rate wireless personal area networks. So if you want to do anything with personal area networks, this would be the place to find out about its secure communication protocols and its api.
#### &nbsp;&nbsp;ant
&nbsp;&nbsp;ANT (Adaptive Network Topology) is a proprietary multicast wireless sensor network technology. So if you need to communcinate with other devices that are using ANT look here.
#### &nbsp;&nbsp;ble
&nbsp;&nbsp;BLE (Bluetooth Low Energy) is one of the best things about the nRF52850 Dongle. This allows it full access to bluetooth networks, meshes, and other forms of bluetooth communications. There is a lot of cool stuff you can do with bluetooth and this device, but I will point out a few of the cool things that the SDK provides (although there is much more):
##### &nbsp;&nbsp;ble_advertising
&nbsp;&nbsp;Bluetooth advertising is when a bluetooth device broadcasts data, either to simply transmit data or to prompt connections. Either way this is one of the most useful parts of bluetooth. Here you will find code (ble_advertising.c file) for everything you might want with bluetooth advertising. There is also the header file (ble_advertising.h) that tells us the data strucutres and more information on the I/O of the code. Below are some great functions:

&nbsp;&nbsp;```C++ addr_is_valid()``` A function to validate a bluetooth address

&nbsp;&nbsp;```C++ on_connected()``` A function to determine the handling of the Connected event in the BLE stack

&nbsp;&nbsp;```C++ on_disconnected()``` A function to determine the handling of the Disconnected event in the BLE stack
##### ble_db_discovery
##### ble_db_discovery


#### boards
#### drivers
#### iot
#### libraries
#### nfc
#### propietary_rf
#### serialization
#### softdevice
#### toolchain


### Config
This section of the SDK contains configuration files. You may need to edit these if you are running into probablems with things referencing each other, but you will most likely not need to touch this folder. 
### Documentation
This section of the SDK contains documentation. If you want to know how something works without trying to decipher it straight from the code found in the components folder, you will probably want to look here.
### Examples
This section of the SDK contains example projects you might want to use, or even try to get comfortable with the board. This is actually an extremely helpful part of the SDK as it allows you to better understand how to utilize the libraries in the components folder, but we will explore this more later on.
### External
This section of the SDK contains files that help you use the SDK in other IDES and in conjunction with external tools. For example, if we wanted to use this SDK with the Segger IDE, which is a pretty common thing, this is where the files are held that tell Segger how to interact with the dongle. 
### External_Tools
This section of the SDK contains a single tool that you run from the command line to connect to other tools through the terminal, but you will most likely not need it regardless of what you are doing. 
### Integration
This section of the SDK is, to the best of my understanding, to help run other versions of the board, or software that was written for other version of the board. It is mainly of use for when you are running multiple devices in a pipeline of sorts, and will most likely not be of use to us. 
### Modules
This section of the SDK seems to be a file for drivers which is defintely not useful for us.

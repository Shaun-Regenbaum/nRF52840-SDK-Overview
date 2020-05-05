# SDK
## What is in it?
### Components
> This section of the SDK contains different APIs, libraries, and functions to use the differnt capabilities of the dongle. There are also the different toolchains for specific softdevices and their APIs. Finally it contains linker files and other files for connecting the SDK to a given toolchain. We wont go through it all, but will go through some important parts of it:
> #### 802_15_4
>> IEEE 802.15.4 is a technical standard which defines the operation of low-rate wireless personal area networks. So if you want to do anything with personal area networks, this would be the place to find out about its secure communication protocols and its api.
> #### ant
>> ANT (Adaptive Network Topology) is a proprietary multicast wireless sensor network technology. So if you need to communcinate with other devices that are using ANT look here.
> #### ble
>> BLE (Bluetooth Low Energy) is one of the best things about the nRF52850 Dongle. This allows it full access to bluetooth networks, meshes, and other forms of bluetooth communications. There is a lot of cool stuff you can do with bluetooth and this device, but I will point out a few of the cool things that the SDK provides (although there is much more):
>> ###### ble_advertising
>>> Bluetooth advertising is when a bluetooth device broadcasts data, either to simply transmit data or to prompt connections. Either way this is one of the most useful parts of bluetooth. Here you will find code (ble_advertising.c file) for everything you might want with bluetooth advertising. There is also the header file (ble_advertising.h) that tells us the data strucutres and more information on the I/O of the code. Below are some great functions:

>>> &nbsp;&nbsp;```C++ addr_is_valid()``` A function to validate a bluetooth address

>>> &nbsp;&nbsp;```C++ on_connected()``` A function to determine the handling of the Connected event in the BLE stack

>>> &nbsp;&nbsp;```C++ on_disconnected()``` A function to determine the handling of the Disconnected event in the BLE stack

>> ###### ble_db_discovery
>>> Bluetooth Database discovery is the way a device gets information from an application's profile. It can look at the UUID's of any service, as well as the charecteristics and properties (I am using all those terms in the formal sense as defined by Bluetooth protocols). A great function is:

>>> &nbsp;&nbsp;```C++ characteristics_discover()``` A function for charecteristic discovery.

>> ###### ble_services
>>> This contains features for BLE that are offered by certain servers and clients. For example, if you want to work with Apple's Notification service, you can find functions in the ble_ancs_c folder (ANCS stands for Apple Notification Center Service).

>> ###### common
>>> This contains common functions that are both used in other places, and functions that you will probably want to use such as scanning functions. Definetly look in here for main things. 

> #### boards
>> This is an EXTREMELY important folder. It contains mappings for all the different boards you may be using. Our nRF52840 dongle is equivalent to a pca10059 board. So if you want to see the relevant pin and component names look in the pca10059.h header file.

>> When you actually want to reference the mappings, you do not need to reference the specific board you are using, rather you can simply refer to the boards.h header file as it contains everything in it.

>> You will also find functions in the board.c file. They are extremely useful. Some examples: 

>> &nbsp;&nbsp;```C++ bsp_board_led_on()``` A function to turn on an led on the board.

>> &nbsp;&nbsp;```C++ gpio_output_voltage_setup(void)``` A function to set GPIO output voltage to 3.0V

>> &nbsp;&nbsp;```C++ bsp_board_buttons_init(void)``` A function to initialize the buttons on the board.

>#### drivers
>> This incorporates the drivers_ext and drivers_nrf folders. These both contain drivers for various peripherals you might use. For example if you want to use radio components you dont have to build the API from scratch it is already done for you. 

#### iot
This contains a whole bunch of stuff. Lets say for some reason you are using the dongle as a controller for a server, there is code for FTP transfer stuff as well as DFU stuff. There is a whole lot of communication code with bigger things. So if you want to do Internet of Things stuff, then look here. 

#### libraries
This contains a whole lot of useful libraries and functions that you may need to use in all your code. If you need timers, the simple_timer library has got you covered. If you need to schedule events, the scheduler library has got you covered. If you want to store stuff on an sd card, we have the sdcard library. If you want to simulate sensors that you don't have, there is the sensorsim library. The list goes on and includes power managment libraries, memory storage libraries, encryption libraries (including sha256), and much more. Make sure to give this folder a look through.

#### nfc
Obviously if you want to do NFC stuff look here.

#### softdevice
This folder contains the pre-built softdevice layers that you can use in the nRF Connect Application. They are essentially protocol stacks that make it easier to use some pre-built peripherals and other stuff. 

#### toolchain
We have already used this folder in out set-up. It contains all the files you need to link, make, etc...  with whatever toolchain you want to use. 

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

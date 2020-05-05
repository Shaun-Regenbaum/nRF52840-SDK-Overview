# SDK
## What is in it?
### Components
This section of the SDK contains different libraries for the differnt peripherals and I/O options that are on the board. It also contains config files, files for compiling, and mre. We wont go through all of them right now, but for example you can see the 'ble' section which contains libraries and functions for the bluetooth low energy (ble) component of the board. You would look inside there for already-built functions and objects that make it a lot easier to utilize the bluetooth capabilities of the board. So this is an important part of the SDK we will explore later.
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

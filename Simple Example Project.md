# Simple Example Project
We are going to make a simple program to make the light on our board flash whenever we click the on-board button. This example is to make sure everything is working correctly. Specifically, we are going to be making a simpler version of the ble_app_blinky example project provided in the SDK.

## Getting Started
To get started, we are going to make a new folder that contains our projects. What we are about to do is not neccesarilly the most effecient way to set up, but it is the fastest. We are going to need to put a couple things in this file:

1) Board Folder
2) eww file
3) Code

To find the board folder we are going to go to ".\SDK\examples\ble_peripheral\ble_app_blinky" folder. There you will find different boards. Our nRF52840 dongle corresponds to the PCA10059 folder. You will copy that folder into your new folder for projects. 

You will also copy the be_app_blinky.eww file you see in the folder. This file just holds references to important ewp files in our working directory, but since we are copying the whole folder, we dont need to change anything there. (If you did not want to have to copy the whole folder, then you could simply change the locations in this eww file). 

You will also see a main.c file there containing code. That is the code for the full example project, but it is a bit overkill for what we want so we are going to leave it. 

Now go back to your fodler where you are going to be holding your pesonal projects. There you will make a main.c file, an example of this is provided in the repository. The code is also provided below:
```C++
#include "boards.h"

int main() {
    bsp_board_init(BSP_INIT_LEDS | BSP_INIT_BUTTONS);
    while (true) {
        if(bsp_board_button_state_get(BSP_BUTTON_0)) {
           bsp_board_led_on(BSP_BOARD_LED_2);
        } else {
            bsp_board_led_off(BSP_BOARD_LED_2);
        }
    }
}
```

## Setting up Make
We are going to need to set up our local makerfie for the project so open up this folder: ".\pca10059\s140\armgcc".
Then open up the makerfile and write the correct SDK root and Project Dir on lines 5 and 6. For me it is this:
```C++
SDK_ROOT := A:\Nordic\SDK
PROJ_DIR := A:\Nordic\Workspace\EX01
```

## Compiling
Now that we have our code and everything set up, we have to generate a hex file in order to upload to our dongle.
You will need to open your terminal and navigate to the ".\pca10059\s140\armgcc" folder. Then you will simply write make on the terminal line and enter. This will generate a hex file that we will upload using nRF Connect.

## Uploading
Now we want to open up nRF-Connect and specfically the Programmer app. You will then Add a Hex file that you generated and simply write it to the device. 

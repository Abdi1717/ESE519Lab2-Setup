# ESE519Lab2-Setup

University of Pennsylvania, ESE 5190: Intro to Embedded Systems, Lab 2 Set-up

    Abdinajib Mohamed
            https://www.linkedin.com/in/abdinajib-mohamed-496436129/
    Tested on: MacBook Air (14-inch, 2021), macOS Monterey 12.5.1



## 1. Installing Homebrew
```bash
     $ /bin/bash -c "$(curl -fsSL
     https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## 2. Installing toolchain
```bash
     $ brew install cmake
     $ brew tap ArmMbed/homebrew-formulae
     $ brew install arm-none-eabi-gcc
```   
     
## 3. Create Pico directory
```bash
     Cd Document
     Mdkir pico
     Cd pico
``` 
 
## 4. Clone Pico-sdk and Pico-examples
```bash
          $ git clone -b master https://github.com/raspberrypi/pico-sdk.git
          $ cd pico-sdk
          $ git submodule update --init
          $ cd ..
          $ git clone -b master https://github.com/raspberrypi/pico-examples.git
```

## 5. Download Visual Studio Code
https://code.visualstudio.com/download


## 6. Install CMake Tools in VSCode
1. Type Cmd+shift+X and search for "CMake Tools"; <br>
2. Click on the entry in the list; <br>
3. Click on the install button; <br>


## 7. Set the Pico_SDK_PATH environment virable
1. Navigate to the pico-examples directory; <br>
2. Create a .vscode directory and add a file called settings.json;<br>
3. Copy these lines to settings.json;<br>

     {
     "cmake.environment": {
         "PICO_SDK_PATH": "../../pico-sdk"
     },
     "C_Cpp.default.configurationProvider": "ms-vscode.cmake-tools"
     }
     

4. Click on the Cog Wheel at the bottom of the navigation bar on the left-hand side of the interface and select "Settings";<br>
5. Click on the "Extensions" and "CMake Tools configuration";<br>
6. Scroll down to " Cmake: Generator: and enter " Unix Makefiles" into the box;<br>


## 8. Add folder to workspace and choose a compiler
Go to the File menu and click on "Add Folder to Workspace..." and navigate to pico-examples repo and click "Okay";<br>
Select "GCC for arm-none-eabi" for compiler";<br>


## 9.Build "Hello World"
cd into pico-examples and create a build directory:<br>
```bash
     $ cd pico-examples
     $ mkdir build
     $ cd build
```    
    
Setting the Pico_SDK_PATH:
```bash
      $ export PICO_SDK_PATH=../../pico-sdk
``` 

run cmake.. :
```bash
     $ cmake ..
``` 

cd into the "hello_world" and run make:
```bash
     $ cd hello_world
     $ make -j4
```     

## 10. Flash and run "Hello World"

1. By holding the "boost" button and press "reset" button at the same time will bring up the RPI;<br>
2. Push "hello_usb.uf2" to RPI;<br>
Enter the console:

```bash
     $ ls /dev/tty.* 
     $ screen /dev/tty.board_name 115200
```
![alt text](https://github.com/Abdi1717/ESE519Lab2-Setup/blob/main/HelloWorldLab2A.png)


# rosserial_stm32f7
Rosserial implementation for STM32F767, developed to work with STM32CubeIDE projects

Heavily based on [yoneken's rosserial_stm32](https://github.com/yoneken/rosserial_stm32)

## Generate code
```
$ cd path/to/your/project/Core

$ rosrun rosserial_stm32f7 make_libraries.py .
```

Note that older versions of STM32CubeIde do not have a "Core" folder, instead "Src" and "Inc" folders are inside the root of your project.
As a general rule you should cd into the folder which has "Src" and "Inc" inside.

## Usage
1. Create a new STM32CubeIDE project:
  * Enable USART3, using PD8 and PD9 as Tx and Rx pins
  * Enable USART3 global interrupt
  * Enable DMA for USART3_TX and USART3_RX and set their priority to HIGH

2. Create ros libraries in your project
```
cd your/catkin/workspace/src
```
```
git clone https://github.com/fdila/rosserial_stm32f7
```
```
cd ..
```
```
catkin_make
```
```
source devel/setup.bash
```
```
cd path/to/your/stm32_project
```
```
rosrun rosserial_stm32f7 make_libraries.py .
```
3. Set header files to be compiled with g++
  * Right click on your project -> Properties
  * C/C++ generals
  * File Types
  * Use project settings
  * New..
  * Pattern: *.h     Type: C++ Header File

4. Convert your stm32 project to C++
  * Right click on your project inside the IDE -> Convert to C++
  * Rename main.c to main.cpp
  
5. On your computer start roscore and rosserial_server:
```
roscore
```
```
rosrun rosserial_server serial_node _port:=/dev/ttyYourBoard _baud:=YourBaudRate
```


**If you have to modify the initial configuration through CubeMX:**
  * Rename main.cpp to main.c
  * Do your changes
  * Repeat step 4

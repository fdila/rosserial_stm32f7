# rosserial_stm32f7
Rosserial implementation for STM32F767, developed to work with STM32CubeIDE projects

Heavily based on [yoneken's rosserial_stm32](https://github.com/yoneken/rosserial_stm32)

## Generate code
```
$ cd path/to/your/project

$ rosrun rosserial_stm32f7 make_libraries.py .
```
## Usage

* Change project type to C++
* Rename main.c to main.cpp
* Set .h files to be compiled with g++

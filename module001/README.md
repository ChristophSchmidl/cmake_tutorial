# Instructions

A simple calculator.

## Compiling manually with just one file: 

```g++ main.cpp -o calculator```

## Compiling manually with multiple files

```g++ main.cpp addition.cpp division.cpp print_result.cpp -o calculator```

## Files needed for compilation

As long as you have the following files, you will be able to compile the project:

- ```main.cpp```
- ```addition.hpp```
- ```division.hpp```
- ```print_result.hpp```
- ```addition.o```
- ```division.o```
- ```print_result.o```

## Other build systems

- Make
- Ninja
- Ant
- Gradle

## Notes about make

Make checks which file you actually changed and only compiles this file again if you invoke ```make```.

## Make vs CMake

- Make: Uses build system files to generate executable.
- CMake: Used to generate build system files (based on the platform/OS that you are using)
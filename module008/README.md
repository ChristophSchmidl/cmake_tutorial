# Module 8 (module 9 in the udemy course)

- Linking external libraries using ```*config``` Module
- Linking external libraries using ```pkg-config``` file
- ```find_library()``` and ```find_path()``` command
- Writing a ```find*cmake``` module

## Commands

- ```find_package(<package_name>)```
- ```find_library(<VAR> <lib-name> <path1> <path2>)```
- ```find_path(...)```

## Using external library

Library name: ```XYZ```
Library name: ```libXYZ.a``` or ```libXYZ.so```

- Download the source code(github/official website)
- ```cmake, make, sudo make install```
- ```XYZ-config.cmake``` in the installed location
- Use ```find_package(XYZ)```

## No ```*config``` module

- Ask the library developers to provide it
- Write your own ```Find*cmake``` file (recommended)
- Write ```*config``` module

## ```*config``` vs ```Find*``` module

- ```*config``` module: Standard directories ```/usr/local```
- ```Find*``` module: Inside your project

## Using external library

- Uses ```CMake based```build generation process
    - ```*config.cmake``` present
    - NO ```*config.cmake``` present
- Uses ```NON-CMake based``` build generation process
    - CMake or library provides ```Find*``` or ```*config``` modules
    - Uses ```pkg-config``` file
    - NO ```pkg-config``` file present

## Variable naming

- Package Name: ```XYZ```
    - Libraries: ```XYZ_LIBRARIES```
    - Include directories: ```XYZ_INCLUDES```

## Files inside packages

- Compiled library
- Header files
- Symbolic links
- Pkg-config (.pc) files

## Pkg-config search directory

- CMake variable: ```CMAKE_PREFIX_PATH```
- Environment variable: ```PKG_CONFIG_PATH```

Always append a path, never rewrite!

- ```set(CMAKE_PREFIX_PATH) ${CMAKE_PREFIX_PATH} "home/user/Desktop"```

## Default paths

- ```find_library(...)```
    - ```/usr/lib```
    - ```/usr/lib/x86_64-linux-gnu```
- ```find_path(...)```
    - ```/usr/include```
    - ```/usr/include/x86_64-linux-gnu```

## ```Find*.cmake``` Module

- ```find_library(...)```
- ```find_library(...)```
- ```find_package_handle_standard_args(...)```
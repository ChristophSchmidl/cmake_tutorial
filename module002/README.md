# Module 2

- CMake installation
- Build file generation
- CMakeLists.txt
- ```add_executable``` command
- Targets
- ```target_link_libraries``` command
- FAQ on targets



## Instructions

Building with CMake:

```
mkdir build
cd build
cmake ..
```

## CMake commands

- ```add_executable(<exec_name> <source_files>)```
- ```add_library(<library_name> <source_files>)```
- ```target_link_libraries(<executable> <lib1> <lib2>)```

## Targets

Targets in CMake can be:

- Libraries
- Executables

Each target can have:

- Properties
- Dependencies

Commond target properties:

- ```INTERFACE_LINK_DIRECTORIES```
- ```INCLUDE_DIRECTORIES```
- ```VERSION```
- ```SOURCES```

CMake commands:

- ```set_target_properties```
- ```set_property```
- ```get_property```
- ```get_target_property```



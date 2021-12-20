# Module 7

- Installing a package
- Exporting a package
- ```install()``` command
- ```find_package()``` command

## Using a package

- Download
- Compile
- Install (Compiled libraries/executables, header files, supporting files)
- Installation path under Linux (/usr/local)

## Commands

- ```install(FILES <file_name> DESTINATION <dir>)```
- ```install(TARGETS <target_name> DESTINATION <dir>)```
- ```find_package(<package_name>)```

## Install command

- Items to copy
- Destination for pasting the items

## Install command destination

- Header files: ```/usr/local/include/<package-name>```
- Targets: ```/usr/local/lib/<package-name>```

## Finding a package

- ```find_package(ABC)``` leads to a search for ```ABC-config.cmake``` inside ```/usr/local/lib/ABC```

## ```find_package()``` command

- Add targets to export group
- Install the export group
- Modify the ```target_include_directories()``` commands

## Modes of operation in ```find_package()```

- Module mode: ```Findmy_math.cmake```
- Config mode: ```my_math-config.cmake```

## Install a third party package

```
find_package(my_math)

if(my_math_FOUND)
    message("my_math library found")
    add_executable(calc main.cpp)
    target_link_libraries(calc my_math)
else()
    message(FATAL_ERROR "my_math library not found")
endif()

message("I forgot to run CMake command")
```
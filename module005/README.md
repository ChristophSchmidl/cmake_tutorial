# Module 5

- Flow Control commands (if-else, loop: while, foreach)
- Function command
- Scopes
- Macro command
- Modules

## Commands

```
if(<condition>)
    <command1>
    <command2>
elseif(<condition>)
    <command3>
else()
    <command4>
endif()
```

```
while(<condition>)
    <commands>
endwhile()
```

```
foreach(<loop_variable> <items>)
    <commands>
endforeach()
```

```
function(<function_name> <function_args>)
    <commands>
endfunction()
```

```
macro(<macro_name> <macro_args>)
    <commands>
endmacro()
```

## Constants

- 1, ON, YES, TRUE, Y, a non-zero number: TRUE
- 0, OFF, NO, FALSE, IGNORE, NOTFOUND, the empty string, string ending with -NOTFOUND: FALSE

## Foreach() command

Start and end are inclusive!

- ```foreach(x RANGE 10)```
- ```foreach(x RANGE 10 20)```
- ```foreach(x RANGE 10 20 3)```
- ```foreach(x IN LISTS <list1> <list2> <list3>)```

## Listfiles and modules

Apart from the listfiles, we also have the concept of modules, where the CMake codes are written. These modules have .cmake extension.



CMake provides some standard modules containing the CMake codes so that we can directly use those in any project. You can find those in the /usr/local/share/CMake-3.16/Modules directory.

These modules can be used with the include() command. If you want to use this module, you need to write these 2 lines of code and then the variable VAR will contain the number of processors.

```
include(ProcessorCount)
ProcessorCount(VAR)
message("Number of processors are: ${VAR}")
```

The modules are often used if we want to have reusable code in our project. Also if your CMakeLists.txt file is too long, some part of it can be written inside another .cmake file; to improve the readability of the code.



## Notes

- ```add_subdirectory()``` and ```function()``` are the only commands which introduce a new scope.
- Macros do not have their own scope but use the parent scope.
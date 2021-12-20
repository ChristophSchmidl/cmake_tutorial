cmake_minimum_required(VERSION 3.0.0)

##############
# DEFINED
##############

if(DEFINED Name)
    message("Name: If block executed")
else()
    message("Name: Else block executed")
endif()

if(DEFINED Age)
    message("Age: If block executed")
else()
    message("Age: Else block executed")
endif()

##############
# COMMAND
##############

if(COMMAND target_link_library)
    message("target_link_library is a command")
else()
    message("target_link_library is NOT a command")
endif()

if(COMMAND target_link_libraries)
    message("target_link_libraries is a command")
else()
    message("target_link_libraries is NOT a command")
endif()

##############
# EXISTS
##############

if(EXISTS ./CMakeLists.txt)
    message("Given file exists")
else()
    message("File not found")
endif()

##############
# String comparison
##############

set(Name1 Alice)
set(Name2 Alice)

if(Name1 STRLESS Name2)
    message("${Name1} is less than ${Name2}")
elseif(Name1 STRGREATER Name2)
    message("${Name1} is greater than ${Name2}")
elseif(Name1 STREQUAL Name2)
    message("${Name1} is equal to ${Name2}")
endif()


##############
# Loops: while
##############

set(LOOPY a)

while(NOT LOOPY STREQUAL "aaaaaaaaa")
    set(LOOPY ${LOOPY}a)
    message(${LOOPY})
endwhile()

##############
# Loops: foreach
##############

foreach(Name Alice Bob Charly)
    message(${Name})
endforeach()

foreach(x RANGE 100 105)
    message("Person_${x}")
endforeach()

set(VAR1 0;1)
set(VAR2 2 3)
set(VAR3 "4 5")

foreach(x IN LISTS VAR1 VAR2 VAR3)
    message("x = ${x}")
endforeach()

##############
# Functions
##############

function(print_detail name_var)
    message("My name is ${name_var}")
endfunction()

function(print_detail_dereference name_var)
    message("My name is ${${name_var}}")
endfunction()

function(print_detail_with_optionals name_var)
    message("My name is ${${name_var}}")

    if(DEFINED ARGV1)
        message("Hello, my name is ${ARGV1}")
    endif()

    message("ARGC= ${ARGC}")
    message("ARGV= ${ARGV}")
    message("ARGN= ${ARGN}")

    if(DEFINED ARGV0)
        message("ARGV0= ${ARGV0}")
    endif()

    if(DEFINED ARGV1)
    message("ARGV1= ${ARGV1}")
    endif()

    if(DEFINED ARGV2)
    message("ARGV2= ${ARGV2}")
    endif()

    if(DEFINED ARGV3)
    message("ARGV3= ${ARGV3}")
    endif()
endfunction()

set(Name Charly)

print_detail(Name)
print_detail_dereference(Name)
print_detail_with_optionals(Name Bob Alice)

##############
# Function scopes
##############

set(Name2 Charly)

function(print_detail2)
    message("Inside function: Before modification: ${Name2}")
    set(Name2 Bob PARENT_SCOPE)
    message("Inside function: After modification: ${Name2}")
endfunction()

message("Outside function: before function call: ${Name2}")
print_detail2()
message("Outside function: after function call: ${Name2}")


##############
# Macros
##############

macro(print_detail_macro name_var)
    message("My name is ${name_var}")
    if(DEFINED name_var)
        message("If block executed.")
    endif()
endmacro()

print_detail_macro(Charly)

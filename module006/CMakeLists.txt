cmake_minimum_required(VERSION 3.0.0)

project(Calculator_Project VERSION 1.0)
###############################################
#               Define subdirectories
###############################################

# Tell CMake to look into the sub dirs and execute
# the CMakeLists.txt in the sub dir. Any library names defined
# in the sub dirs are also available to the parent CMakeLists.txt
add_subdirectory(my_math)
add_subdirectory(my_print)


###############################################
#               Create executable
###############################################
add_executable(calculator main.cpp)

###############################################
#         Link libraries to executable
###############################################
target_link_libraries(calculator PRIVATE my_math my_print)

###############################################
#         Setting cache variables
###############################################
set(A "123" CACHE STRING "This command sets variable A in persistent cache")

message($CACHE{A})

###############################################
#         Setting environment variables
###############################################
set(ENV{B} 1337)

message($ENV{B})

###############################################
#         Mofification of cache variables
###############################################
set(Name Alice CACHE STRING "The name variable")
set(Name BOB CACHE STRING "The modified name variable")
message($CACHE{Name})

# Use -DName=Bob to override that

###############################################
#         Common cache variables
###############################################
message(CMAKE_VERSION=${CMAKE_VERSION})
message(CMAKE_MAJOR_VERSION=${CMAKE_MAJOR_VERSION})
message(CMAKE_MINOR_VERSION=${CMAKE_MINOR_VERSION})
message(CMAKE_PATCH_VERSION=${CMAKE_PATCH_VERSION})

message("Root level CMakeLists: CMAKE_PROJECT_NAME=${CMAKE_PROJECT_NAME}")
message("Root level CMakeLists: PROJECT_NAME=${PROJECT_NAME}")


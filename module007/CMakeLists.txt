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
#                   Packages
###############################################
message(${CMAKE_INSTALL_PREFIX})
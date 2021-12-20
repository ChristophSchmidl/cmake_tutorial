cmake_minimum_required(VERSION 3.0.0)

project(Calculator_Project VERSION 1.0)
###############################################
#               Create libraries
###############################################

add_library(my_math addition.cpp division.cpp)
add_library(my_print print_result.cpp)

###############################################
#               Create executable
###############################################
add_executable(calculator main.cpp)

###############################################
#         Link libraries to executable
###############################################
target_link_libraries(calculator my_math my_print)
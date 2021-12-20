# Module 6

## Global Scope

- Persistent Cache Variables
- Environment Variables

## Cache Variables

- Set by Cmake, depending on the Development environment
- Set by commands inside CMakeLists.txt

## Environment variables

- Global scope
- Not stored in CMakeCache.txt

## Commands

- ```set(ENV <variable_name> <variable_value>)```
- ```$ENV{variable_name}```

## Modifying cache variables

1. Run CMake command for the first time
2. CMakeCache.txt created
3. Modify/Remove previous cache variables (gets rejected)

There are three options to override the CMakeCache.txt

1. Edit ```CMakeCache.txt``` directly
2. Use ```Force``` keyword (not recommended)
3. Use ```-D``` flag

## Most common cache variables

- ```CMAKE_VERSION```
- ```CMAKE_MAJOR_VERSION```
- ```CMAKE_MINOR_VERSION```
- ```CMAKE_PATCH_VERSION```
- ```CMAKE_PROJECT_NAME```
- ```PROJECT_NAME```
- ```CMAKE_GENERATOR```

## Changing the generator

- ```cmake -DCMAKE_GENERATOR=Ninja ..```
- ```cmake -GNinja ..```


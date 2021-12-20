# cmake_tutorial
Simple cmake snippets for C++

## Requirements

### Ubuntu

On a **Ubuntu machine**, you can just install the build-essential package which includes a lot of packages like gcc, g++ and make. Additionally, you have to install cmake.

```
sudo apt update
sudo apt install build-essential
sudo apt install cmake
```

### Mac

On a Mac, you probably already have all required build tools except cmake. The easiest way to install CMake on a Mac is using homebrew:

```
brew install cmake
```
## Requirements to run CMake

- A ```CMakeLists.txt```
- Any directory to store the generated build files (e.g. ```/build```)

## FAQ

- Can we have 2 targets of the same name?
    - Answer: No

- Do we have the target files saved on our computer?
    - Answer: Yes, you should normally find them in the build directory with prefix ```lib``` for libraries + name of the target + suffix ```.a```
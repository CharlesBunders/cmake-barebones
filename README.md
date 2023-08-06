# CMake Barebones 

A minimal CMake project for C++.

This project is useful as a quick starting point for a command line C++ project or for learning the basics of CMake.

# Usage

Clone the project, then:

```sh
mkdir build
cd build
cmake ..
cmake --build .
```

Should end up with an executable you can run under the build directory in:

```sh
./src/Debug/barebones.exe  <-- Windows
./src/barebones            <-- Linux
```

## Changing the Projects Name

Linux:
(In the root directory before running cmake)
```sh
grep --include CMakeLists.txt -ElRZ 'barebones' | xargs -0 -l sed -i -e 's/\bbarebones\b/YOURPROJECTNAME/g'
```

Or just change the word "barebones" in the CMakeLists.txt in the root directory and
the CMakeLists.txt file in the /src directory to whatever name you wish.

# If New to CMake

CMake provides a way to create and perform compiler independant builds from configuration files.
The configuration file CMakeLists.txt contains the configuration but will likely point
to other directories/projects/libraries that contain more CMakeLists.txt files.

To see what generators are available try:

```sh
cmake --help
```

There will likely be a default already set for the system you are on.
However, to explicitly set different generators try:

```sh
cmake -G "Visual Studio 17 2022"
```

Also setting the architecture instead of using the default:
```sh
cmake -G "Visual Studio 17 2022" -A Win32
cmake -G "Visual Studio 17 2022" -A x64
cmake -G "Visual Studio 17 2022" -A ARM
cmake -G "Visual Studio 17 2022" -A ARM64
```

A full example on Windows generating and building from a created build directory in the cloned folder:
```sh
cmake -G "Visual Studio 17 2022" -A x64 ..
cmake --build . --config MINSIZEREL
```
Linux (static lib's):
```sh
cmake .. -D LINK_DEPS_STATIC=ON -D BUILD_SHARED_LIBS=FALSE 
cmake --build . --config DEBUG
```

Another file to be aware of is the CMakeCache.txt file. This will be in your
build directory after running cmake. If you make changes and want to 
generate your build files again just delete the CMakeCache.txt file.

# Project provided by:

[Xhana Labs](https://www.xhanalabs.com) 

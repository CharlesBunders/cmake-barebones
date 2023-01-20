# CMake Barebones 

A minimal CMake project for C++.

This project is useful as a quick starting point or for learning the basics of CMake.

# Usage

Clone the project then:

```sh
mkdir build
cd build
cmake ..
cmake --build .
```

## Changing the projects name

Linux:
```sh
grep -ElRZ 'barebones' CMakeLists.txt | xargs -0 -l sed -i -e 's/\bbarebones\b/YOURPROJECTNAME/g'
```

Or just change the word "barbones" in the CMakeLists.txt in the root directory and
the CMakeLists.txt file in the /src directory.

# If New to CMake

CMake provides a way to create and perform compiler independant builds from configuration files.
The configuration file CMakeLists.txt contains the configuration but will likely point
to other directories/projects/libraries that contain more CMakeLists.txt files.

To see what generators are available try:

```sh
cmake --help
```

There will likely be a default set for the system you are on.
To explicitly set the generator try:

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

Another file to be aware of is the CMakeCache.txt file. This will be in your
build directory after running cmake. If you make changes and want to 
generate your build files again just delete the CMakeCache.txt file.

# Project provided by:

[Xhana Labs](https://www.xhanalabs.com) 

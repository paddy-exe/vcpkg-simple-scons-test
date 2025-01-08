# Vcpkg package manager library integration with scons
This project is an example on how libraries built via the vcpkg package manager with the cmake build-system could be integrated into a C++ program built using the scons build-system. It is part of a blog post of mine explaining how to use the scons build-system either manually with cmake built libraries and package managers such as vcpkg and conan.

## Build requirements
- vcpkg
- Python
- SCons
- CMake
- C++ compiler

## Build instructions
1. In the root directory, install the libraries specified by the `vcpkg.json` file (here the `fmt` library)
```sh
vcpkg install
```

2. Call `scons` to compile the program into the executable `helloworld`
```sh
scons
```

3. Run program (This may differ slightly on Windows)
```sh
./helloworld
```

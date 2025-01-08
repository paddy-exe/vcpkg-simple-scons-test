#!/usr/bin/env python
import os
import sys

env = Environment()

# Glob search through source files given a specific pattern
sources = Glob("src/*.cpp")

if sys.platform == "darwin":
    vcpkg_lib_path = "vcpkg_installed/"
    env.Append(CPPPATH=["vcpkg_installed/arm64-osx/include"])
    env.Append(LIBPATH="vcpkg_installed/arm64-osx/lib/")
elif sys.platform == "win32" or sys.platform == "msys":
    env.Append(CPPPATH=["vcpkg_installed/x64-windows/include"])
    env.Append(LIBPATH="vcpkg_installed/x64-windows/lib/")
elif sys.platform == "linux":
    env.Append(CPPPATH=["vcpkg_installed/x64-linux/include"])
    env.Append(LIBPATH="vcpkg_installed/x64-linux/lib/")
else:
    print("Your system is not supported by the the SConstruct file. Exciting.")
    env.Exit(1)

# set c++ standard to 11
env.Append(CXXFLAGS=['-std=c++11'])

# set name of library/ies to be linked
env.Append(LIBS=["libfmt"])

# Create a runnable program given the source files with all their dependencies
env.Program("helloworld", sources)

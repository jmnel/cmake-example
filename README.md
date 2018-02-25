# cmake-example
CMake example project with one executable.

This is a minimal example cmake project. It is intended to be the starting point for a beginner,
that is starting to learn to setup cmake to build C++ projects.

A simple project directory could look something like this:

+--bin
|   |
|   +--Debug
|   +--Release
|
+--build
|
+--doc
|
+--src
    |
    +--target0

To build this project. Create a folder named 'build' in the root project directory( where this 
README is located). Once inside this folder, run

$   cmake ../src

This will configure the build system. Now, to actually build the project, run

$   make

This will run the compiler. If the build succeeds, the executable 'tutorial0' will be copied to
'bin/Debug/tutorial0'. You can run it with

$   ../bin/Debug/tutorial0


This is the first in a series of example cmake projects, that I will publish here, along with
a blog. Hopefully this can save a beginner some time, searching through documentation, in order
to help them figure what is the best way to build projects with cmake.

For any corrections or improvements, please initiate a pull request.

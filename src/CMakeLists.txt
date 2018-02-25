# Set cmake minimum required version.
cmake_minimum_required( VERSION 3.4 FATAL_ERROR )

# Create new project. Replace <project_name> with your project's name.
project( project_name VERSION 0.1 LANGUAGES CXX )

set( CMAKE_CXX_STANDARD 17 )            # C++ standard, 98, 11, 14, or 17
set( CMAKE_CXX_STANDARD_REQUIRED ON )   # Enforces above standard
#set( CMAKE_CXX_EXTENSIONS OFF )        # Disable non-standard langauge exentions for portability
set( CMAKE_BUILD_TYPE Debug )           # Set build type: Debug or Release

# Set your compiler warning flags here. It's a good idea to enable as many compiler warnings
# as possible. Refer to Clang documentation:
# https://clang.llvm.org/docs/DiagnosticsReference.html
set( WARNING_FLAGS
    "-Wall "
    "-Werror=return-type "
    "-Wextra "
    "-Wmissing-field-initializers "
    )

# Other compiler flags.
set( MISC_FLAGS
    "-pedantic "    # tell compiler to strictly adhere to ANSI language standard.
    "-O2 "          # performance optimization level.
    )

# Combine above 2 arrays into strings.
string( CONCAT WARNING_FLAGS_ALL ${WARNING_FLAGS} )
string( CONCAT MISC_FLAGS_ALL ${MISC_FLAGS} )

# Combine 2 strings obtained above to set compiler flags.
set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}${MISC_FLAGS_ALL}${WARNING_FLAGS_ALL}" )

# This command copies your executable build product to bin/Debug folder.
set( CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/../bin/Debug )

# This location is where cmake searches for extra modules, for example scripts to find libraries.
set( CMAKE_MODULE_PATH ${CMAKE_CURRENT_LIST_DIR}/cmake/modules )

# Export compile commands to 'compile_commands.json' for use with tools like YouCompleteMe
set( CMAKE_EXPORT_COMPILE_COMMANDS ON )

# Add libraries that are needed by your project here.
# Example: Add OpenGL like this.
find_package( OpenGL REQUIRED )

# Add sub directories containing other CMakeLists.txt here.
# In this example we are building a single executable called tutorial0.
add_subdirectory( ${CMAKE_CURRENT_LIST_DIR}/tutorial0 )

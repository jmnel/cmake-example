# This array is a list of all your '.cpp' source files. Add them after 'Main.cpp'.
set( SRC_FILES Main.cpp )

# Add executable build product to project. The add all '.cpp' files after 'Main.cpp', from above 
# array so that they are passed to the compiler.
add_executable( tutorial0 ${SRC_FILES} )

# Set compile options for above build target.
target_compile_options( tutorial0 PUBLIC ${DEBUG_FLAGS} )

# Include directories for #include <...> statements here. Also link libraries here which your project
# uses.

# Example: Link OpenGL
# target_link_libraries( tutorial0 ${OPENGL_gl_LIBRARY} )

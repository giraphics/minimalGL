# Projects Settings 

cmake_minimum_required (VERSION 3.1) 

project (opengl-dev) 

  

add_definitions(-DGLEW_STATIC) 
add_subdirectory(lib/glfw EXCLUDE_FROM_ALL) 
add_subdirectory(lib/glew EXCLUDE_FROM_ALL) 
add_subdirectory(lib/glm EXCLUDE_FROM_ALL) 
  

# All libraries - GLFW, glew, glm 
set(ALL_LIBS 
  PRIVATE glfw 
  PRIVATE libglew_static 
  PRIVATE glm 
) 
  

# -0
add_executable(tut-0 
  main.cpp 
) 

target_link_libraries(tut-0 
${ALL_LIBS} 
) 

set_property(TARGET tut-0 PROPERTY CXX_STANDARD 11) 
target_compile_options(tut-0 PRIVATE -Wall) 
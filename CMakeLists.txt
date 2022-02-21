cmake_minimum_required(VERSION 3.10)
set (CMAKE_CXX_STANDARD 11)

# set the project name
project(gl_proj)

# add the executable
add_executable(gl_proj main.cpp glad/src/glad.c)

include_directories(glfw/deps)
include_directories(glad/include)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(glfw)
target_link_libraries(gl_proj glfw)
cmake_minimum_required(VERSION 3.17)
# Set project name
set(PROJECT_NAME "test_opengl")
project(${PROJECT_NAME})
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
find_package(OpenGL REQUIRED)
# Including GLFW
add_subdirectory(glfw)
include_directories(glfw/include)
# Including GLAD
include_directories(glad/include)
set(SOURCE_FILES main.cpp glad/src/glad.c)
add_executable(${PROJECT_NAME} ${SOURCE_FILES})
# Linking GLFW and OGL
target_link_libraries(${CMAKE_PROJECT_NAME} glfw ${GLFW_LIBRARIES} ${OPENGL_LIBRARY})
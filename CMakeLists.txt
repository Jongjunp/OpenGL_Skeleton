cmake_minimum_required(VERSION 3.2)
project(obj-viewer)

set(CMAKE_CXX_COMPILER "g++")

find_package(OpenGL REQUIRED)
set(GLUT_LIBRARIES /opt/homebrew/lib/libglut.3.dylib)
set(GLUT_INCLUDE_DIRS /opt/homebrew/include)
set(GLUT_LIBRARY_DIRS /opt/homebrew/lib)

set(SOURCE_FILES obj-viewer.cpp)
add_executable(obj-viewer ${SOURCE_FILES})
include_directories(${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS})
ADD_COMPILE_OPTIONS ( "-g" )

target_link_libraries(obj-viewer ${OPENGL_LIBRARIES} ${GLUT_LIBRARIES})
target_compile_options(obj-viewer PUBLIC -Wno-deprecated-declarations)
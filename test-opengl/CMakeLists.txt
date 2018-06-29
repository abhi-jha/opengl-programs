cmake_minimum_required(VERSION 3.10)
project(test_opengl)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -pthread -fpermissive  -lGL -lGLU -lglut -lGLEW")
find_package (PkgConfig REQUIRED)
find_package (OpenGL REQUIRED)
find_package (GLUT REQUIRED)
set(GLEW_INCLUDE_DIR, "/home/user/Music/glew-2.1.0/include/")
set(GLEW_LIBRARY, "/home/user/Music/glew-2.1.0/lib/")

include_directories(${OPENGL_INCLUDE_DIR}  ${GLUT_INCLUDE_DIRS})

file(GLOB SOURCE_FILES
        *.cpp
        *.h
        )

add_executable(test_opengl ${SOURCE_FILES})

target_link_libraries (test_opengl ${OPENGL_LIBRARIES} ${GLUT_LIBRARIES} GL m dl Xinerama Xrandr Xi Xcursor X11 Xxf86vm pthread)
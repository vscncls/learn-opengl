cmake_minimum_required(VERSION 3.29)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(learnOpenGL VERSION 1.0)

find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)

file(GLOB_RECURSE SRC_FILES CONFIGURE_DEPENDS src/*.c src/*.h src/*.cpp src/*.hpp)
add_executable(learnOpenGL src/main.cpp)

add_subdirectory(lib/glad/)

target_link_libraries(learnOpenGL glad)
target_link_libraries(learnOpenGL glfw)
target_link_libraries(learnOpenGL OpenGL::GL)

target_include_directories(learnOpenGL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

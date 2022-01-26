cmake_minimum_required(VERSION 3.15)
set(CMAKE_CXX_STANDARD 20)

project(plugin)
add_library(plugin SHARED main.cpp impl.cpp natives.cpp)

target_include_directories(plugin PUBLIC sdk)
target_link_libraries(plugin PUBLIC sdk)

if(CMAKE_COMPILER_IS_GNUCC OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
	set_property(TARGET plugin APPEND_STRING PROPERTY COMPILE_FLAGS " -m32")
	set_property(TARGET plugin APPEND_STRING PROPERTY LINK_FLAGS    " -m32")
endif()
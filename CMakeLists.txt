cmake_minimum_required(VERSION 3.15)
set(CMAKE_CXX_STANDARD 20)

# -
# main project
# -
project(plugin-template)

# -
# global configuration
# -
if(UNIX)
	set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/build/linux32/${CMAKE_BUILD_TYPE})
else()
	set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/build/win32/${CMAKE_BUILD_TYPE})
	# set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /MD")
endif()

# -
# dependencies
# -
add_subdirectory(vendor/sdk)

# -
# projects
# -
add_subdirectory(source/plugin)
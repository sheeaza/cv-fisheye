cmake_minimum_required(VERSION 3.5)

project(fisheye)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

#fix stdlib.h not found issue
set(CMAKE_NO_SYSTEM_FROM_IMPORTED 1)

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug)
endif()

set(CMAKE_INSTALL_PREFIX ${PROJECT_BINARY_DIR}/${CMAKE_BUILD_TYPE})

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ReplxxConfig)

add_subdirectory(src)
add_subdirectory(thirdparty/replxx EXCLUDE_FROM_ALL)


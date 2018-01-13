cmake_minimum_required(VERSION 3.5.1)
project(drake-kuka-driver)

# set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/modules")
# if(NOT EXISTS ${CMAKE_SOURCE_DIR}/cmake/modules/FindGFlags.cmake)
#   message(FATAL_ERROR "\nThe kuka-fri submodule is not available.\nPlease run: git submodule update --init or install the FRI source (see README.md).")
# endif()

set(EXECUTABLE_OUTPUT_PATH "${CMAKE_BINARY_DIR}/bin")
set(LIBRARY_OUTPUT_PATH "${CMAKE_BINARY_DIR}/lib")

set(CMAKE_INSTALL_RPATH "${CMAKE_INSTALL_PREFIX}/lib")
set(CMAKE_INSTALL_NAME_DIR ${CMAKE_INSTALL_RPATH})

if(NOT EXISTS ${CMAKE_SOURCE_DIR}/kuka-fri/src)
  message(FATAL_ERROR "\nThe kuka-fri submodule is not available.\nPlease run: git submodule update --init or install the FRI source (see README.md).")
endif()

add_subdirectory(kuka-driver)

# get_cmake_property(_variableNames VARIABLES)
# foreach (_variableName ${_variableNames})
#     message(STATUS "${_variableName}=${${_variableName}}")
# endforeach()

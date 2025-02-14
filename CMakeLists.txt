cmake_minimum_required(VERSION 3.5)
project(maxLibQt)

set(CMAKE_COLOR_MAKEFILE ON)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/bin)

set(SRC_DIR "${PROJECT_SOURCE_DIR}/src")
set(DOC_DIR "${PROJECT_SOURCE_DIR}/doc")

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Core)

## Subprojects
add_subdirectory("${SRC_DIR}")

## Doxymentation
add_subdirectory("${DOC_DIR}")

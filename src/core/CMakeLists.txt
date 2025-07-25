cmake_minimum_required(VERSION 3.5)
cmake_policy(SET CMP0020 NEW)
set(CMAKE_CXX_STANDARD 17)

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Core)

project(maxLibQtCore)

set(SRCS
	"${CMAKE_CURRENT_LIST_DIR}/AppDebugMessageHandler.cpp"
)

set(HDRS
	"${CMAKE_CURRENT_LIST_DIR}/AppDebugMessageHandler.h"
)

qt_wrap_cpp(SRCS ${HDRS})

add_library(${PROJECT_NAME} ${SRCS} ${HDRS})
target_link_libraries(${PROJECT_NAME} PRIVATE Qt::Core)
target_compile_definitions(${PROJECT_NAME} PRIVATE QT_USE_QSTRINGBUILDER)
target_include_directories(${PROJECT_NAME} PUBLIC "${CMAKE_CURRENT_LIST_DIR}")

# need to push this upstream
set(BUILT_LIBRARIES ${BUILT_LIBRARIES} ${PROJECT_NAME} PARENT_SCOPE)

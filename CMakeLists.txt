# /CMakeLists.txt
# Created by Robin Rowe 2022-07-13
# License: QuickJS Javascript Engine

cmake_minimum_required(VERSION 3.21)

project(QuickJS)
message("Configuring ${PROJECT_NAME}...")

set(LIBUNISTD_PATH /code/github/libunistd)
if(WIN32)
	include_directories(${LIBUNISTD_PATH}/unistd)
	link_directories(${LIBUNISTD_PATH}/build/${CMAKE_GENERATOR_PLATFORM})
	link_libraries(libunistd)
endif(WIN32)

file(STRINGS sources.cmake SOURCES)
add_library(${PROJECT_NAME}_lib ${SOURCES})
link_libraries(${PROJECT_NAME}_lib)
add_subdirectory(examples tests)
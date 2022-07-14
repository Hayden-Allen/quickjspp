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

add_definitions(-DCONFIG_BIGNUM)
file(STRINGS sources.cmake SOURCES)
add_library(${PROJECT_NAME}_lib ${SOURCES})
link_libraries(${PROJECT_NAME}_lib)
add_subdirectory(examples tests)
add_executable(jscompress jscompress.c)
add_executable(libregexp libregexp.c)
add_executable(qjs qjs.c)
add_executable(qjsc qjsc.c)
add_executable(run-test262 run-test262.c)
add_executable(unicode_gen unicode_gen.c)

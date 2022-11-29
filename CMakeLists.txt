# QuickJS/CMakeLists.txt
# Created by Robin Rowe 2022-11-28
# License: QuickJS Javascript Engine

cmake_minimum_required(VERSION 3.8)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

project(QuickJSapp)
message("Configuring ${PROJECT_NAME}...")
enable_testing()
file(STRINGS sources.cmake SOURCES)
if(NOT WIN32 AND NOT APPLE)
	link_libraries(rt pthread)
endif(NOT WIN32 AND NOT APPLE)

option(UNISTD "Enable libunistd" true)
if(UNISTD)
	set(LIBUNISTD_PATH /code/github/libunistd)
	if(WIN32)
		include_directories(${LIBUNISTD_PATH}/unistd)
		link_directories(${LIBUNISTD_PATH}/build/x64/Debug/)
		link_libraries(libunistd)
	endif(WIN32)
endif(UNISTD)

add_definitions(-DCONFIG_BIGNUM)
file(STRINGS sources.cmake SOURCES)
add_library(${PROJECT_NAME}_lib ${SOURCES})
link_libraries(${PROJECT_NAME}_lib)
add_subdirectory(examples tests)

add_executable(jscompress jscompress.c)
add_executable(qjs qjs.c)
add_executable(qjsc qjsc.c)
add_executable(run-test262 run-test262.c)
add_executable(unicode_gen unicode_gen.c)

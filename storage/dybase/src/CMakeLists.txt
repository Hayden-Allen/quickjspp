# storage/dybase/src/CMakeLists.txt
# Created by Robin Rowe 2022-07-13
# License: QuickJS Javascript Engine

project(storage/dybase/src)
message("Configuring ${PROJECT_NAME}...")

file(STRINGS sources.cmake SOURCES)
add_library(${PROJECT_NAME}_lib ${SOURCES})
link_libraries(${PROJECT_NAME}_lib)

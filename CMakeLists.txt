cmake_minimum_required(VERSION 2.8.4)
project(bitcoin)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -ggdb")
set(PROJECT_SOURCE_DIR "..")

aux_source_directory(./src PROJECT_SOURCE_FILES)

add_custom_target(bitcoin COMMAND make
        CLION_EXE_DIR=${PROJECT_SOURCE_DIR}
        WORKING_DIRECTORY ${PROJECT_SOURCE_DIR}
        SOURCES ${PROJECT_SOURCE_FILES})

add_custom_target(fake COMMAND ls
        SOURCES ${PROJECT_SOURCE_FILES})

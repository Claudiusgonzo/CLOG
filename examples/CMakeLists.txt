cmake_minimum_required (VERSION 3.5 FATAL_ERROR)
project (clogexamples)

set(CMAKE_CLOG_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bld/clog)
set(CMAKE_CLOG_BINS_DIRECTORY ${CMAKE_SOURCE_DIR}/artifacts/tools/bin/clog)
set(CMAKE_CLOG_SIDECAR_DIRECTORY ${CMAKE_SOURCE_DIR}/examples/sidecar)
set(CMAKE_CLOG_CONFIG_FILE ${CMAKE_SOURCE_DIR}/clog_examples.clog_config)
set(CMAKE_CLOG_GENERATE_FILE ${CMAKE_BINARY_DIR}/clog/CLog.cmake)
set(CLOG_INCLUDE_DIRECTORY ${CMAKE_BINARY_DIR}/clog)

if (WIN32)
    set(CMAKE_CLOG_CONFIG_PROFILE windows)
elseif (APPLE)
    set(CMAKE_CLOG_CONFIG_PROFILE macos)
elseif (UNIX)
    set(CMAKE_CLOG_CONFIG_PROFILE linux)
endif()

add_subdirectory (clogsample)

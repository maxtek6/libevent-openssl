cmake_minimum_required(VERSION 3.0)

project(libevent-openssl)

file(COPY_FILE ${CMAKE_CURRENT_SOURCE_DIR}/LibeventCMakeLists.txt ${CMAKE_CURRENT_SOURCE_DIR}/libevent/CMakeLists.txt)

add_subdirectory(openssl-cmake)

set(EVENT__DISABLE_MBEDTLS ON CACHE BOOL "")
set(EVENT__DISABLE_TESTS ON CACHE BOOL "")
set(EVENT__DISABLE_REGRESS ON CACHE BOOL "")
set(EVENT__DISABLE_BENCHMARK ON CACHE BOOL "")
set(EVENT__DISABLE_SAMPLES ON CACHE BOOL "")
add_subdirectory(libevent)
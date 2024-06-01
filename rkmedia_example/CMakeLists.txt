cmake_minimum_required(VERSION 2.8...3.13)

if(NOT CMAKE_BUILD_TYPE)
    message(STATUS "Build type not defined. Set 'CMAKE_BUILD_TYPE=Release' force ")
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Set Release force " FORCE)
endif()

project(vi_vo_test C CXX)

include(cmake/rkaiq.cmake)
add_definitions(-DRKAIQ)

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 11)

include_directories(
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${CMAKE_CURRENT_SOURCE_DIR}/common)

add_executable(vi_vo_test
        ${CMAKE_CURRENT_SOURCE_DIR}/rkmedia_vi_vo_test.c
        ${CMAKE_CURRENT_SOURCE_DIR}/common/sample_common_isp.c)

target_link_libraries(vi_vo_test easymedia ${RKAIQ_LIBRARY})

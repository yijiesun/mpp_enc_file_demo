cmake_minimum_required(VERSION 2.8)

project(mpp_demo)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES main.c
        thread/Thread.cpp
        rkrga/RGA.cpp
        mpp/utils/mpi_enc_utils.c
        mpp/utils/mpi_dec_utils.c
        mpp/utils/utils.c
        mpp/utils/iniparser.c
        mpp/utils/dictionary.c
        mpp/utils/camera_source.c
        )
include_directories(
        ${CMAKE_CURRENT_SOURCE_DIR}/mpp
        ${CMAKE_CURRENT_SOURCE_DIR}/mpp/osal
        ${CMAKE_CURRENT_SOURCE_DIR}/mpp/utils
        )
add_executable(mpp_demo ${SOURCE_FILES})
target_link_libraries(mpp_demo rockchip_mpp pthread)
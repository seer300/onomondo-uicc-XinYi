# Copyright (c) 2024 Onomondo ApS. All rights reserved.
# SPDX-License-Identifier: GPL-3.0-only

add_subdirectory(crypto)
add_subdirectory(milenage)
add_subdirectory(uicc)

add_library(storage STATIC storage.c fs.c)
target_compile_options(storage PRIVATE ${PRJ_COMPILE_OPTIONS_LIST})
target_include_directories(storage PUBLIC ${CMAKE_SOURCE_DIR}/include)
target_include_directories(storage PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../../include)

# 创建输出目录
file(MAKE_DIRECTORY ${LIB_DIR})
set_property(TARGET storage APPEND PROPERTY 
ARCHIVE_OUTPUT_DIRECTORY ${LIB_DIR})
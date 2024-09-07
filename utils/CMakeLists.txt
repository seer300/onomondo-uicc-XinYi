# Copyright (c) 2024 Onomondo ApS. All rights reserved.
# SPDX-License-Identifier: GPL-3.0-only

set(utils_collection
	ss_profile.c
)

add_library(utils STATIC ${utils_collection})
target_compile_options(utils PRIVATE ${PRJ_COMPILE_OPTIONS_LIST})

target_include_directories(utils
	PUBLIC
		${CMAKE_SOURCE_DIR}/include
)
target_include_directories(utils PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../include)

# 创建输出目录
file(MAKE_DIRECTORY ${LIB_DIR})
set_property(TARGET utils APPEND PROPERTY 
ARCHIVE_OUTPUT_DIRECTORY ${LIB_DIR})
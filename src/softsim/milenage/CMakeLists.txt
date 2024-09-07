# Copyright (c) 2024 Onomondo ApS. All rights reserved.
# SPDX-License-Identifier: GPL-3.0-only

add_library(milenage 
	STATIC 
		milenage.c 
		milenage_usim.c
)
target_compile_options(milenage PRIVATE ${PRJ_COMPILE_OPTIONS_LIST})

target_include_directories(milenage
	PUBLIC
		${CMAKE_SOURCE_DIR}/include
	PRIVATE
		${CMAKE_CURRENT_SOURCE_DIR}
		${CMAKE_CURRENT_SOURCE_DIR}/../
		${CMAKE_CURRENT_SOURCE_DIR}/../../../include
)

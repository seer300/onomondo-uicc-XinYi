# Copyright (c) 2024 Onomondo ApS. All rights reserved.
# SPDX-License-Identifier: GPL-3.0-only

add_library(crypto 
	STATIC
		aes-encblock.c
		aes-internal-dec.c
		aes-internal-enc.c
		aes-internal.c
		aes-wrap.c
		des-internal.c
)
target_compile_options(crypto PRIVATE ${PRJ_COMPILE_OPTIONS_LIST})

target_include_directories(crypto
	PUBLIC
		${CMAKE_SOURCE_DIR}/include
	PRIVATE
		${CMAKE_CURRENT_SOURCE_DIR}
		${CMAKE_CURRENT_SOURCE_DIR}/../../../include
)

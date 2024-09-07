# Copyright (c) 2024 Onomondo ApS. All rights reserved.
# SPDX-License-Identifier: GPL-3.0-only

set(uicc_collection
	access.c
	apdu.c
	btlv_enc.c
	btlv_dec.c
	btlv_utils.c
	ctlv.c
	command.c
	df_name.c
	fcp.c
	file.c
	fs.c
	fs_chg.c
	fs_utils.c
	uicc_lchan.c
	sfi.c
	sms.c
	sw.c
	softsim.c
	tlv8.c
	uicc_admin.c
	uicc_auth.c
	uicc_cat.c
	uicc_sms_rx.c
	uicc_sms_tx.c
	uicc_remote_cmd.c
	uicc_file_ops.c
	uicc_pin.c
	uicc_refresh.c
	utils.c
	utils_ota.c
	utils_3des.c
	utils_aes.c
	proactive.c
	uicc_suspend.c
)

# Combine UICC with or without testing required files
add_library(uicc STATIC ${uicc_collection})
target_compile_options(uicc PRIVATE ${PRJ_COMPILE_OPTIONS_LIST})

target_include_directories(uicc
	PUBLIC
		${CMAKE_SOURCE_DIR}/include
	PRIVATE
		${CMAKE_CURRENT_SOURCE_DIR}
		${CMAKE_CURRENT_SOURCE_DIR}/../
		${CMAKE_CURRENT_SOURCE_DIR}/../../../include
)

# 创建输出目录
file(MAKE_DIRECTORY ${LIB_DIR})
set_property(TARGET uicc APPEND PROPERTY 
ARCHIVE_OUTPUT_DIRECTORY ${LIB_DIR})
add_subdirectory(src)

set(CORE cortex-m3)
list(APPEND PRJ_COMPILE_OPTIONS_LIST
	"-mthumb"
	"-mcpu=${CORE}"
	"-O2"
	"-Os"
	"-fmessage-length=0"
	"-fsigned-char"
	"-ffunction-sections"
	"-fdata-sections"
	"-ffreestanding"
	"-Wall"
	"-Wextra"
	"-g"
	"-nostartfiles"
)
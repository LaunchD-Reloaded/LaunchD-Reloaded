add_library(OpenXPC log.c procutil.c xpc_array.c xpc_dbus.c xpc_dictionary.c
	xpc_misc.c xpc_type.c)
target_link_libraries(OpenXPC PkgConfig::DBUS sbuf)
target_include_directories(OpenXPC
	PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
		$<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}>)
target_compile_options(OpenXPC PRIVATE -fblocks)

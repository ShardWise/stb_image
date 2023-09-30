cmake_minimum_required (VERSION 3.8)
project(stb_image)

add_library(stb_image STATIC "stb_image.h" "stb_image.cpp")
set_target_properties(stb_image PROPERTIES LINKER_LANGUAGE CXX)

target_include_directories(stb_image PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")

if(WIN32)
	set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()
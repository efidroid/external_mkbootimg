cmake_minimum_required(VERSION 2.8)

# common
project(mkbootimg)
set(CMAKE_BUILD_TYPE Release)
set(CMAKE_C_FLAGS "-Wall -Wextra -Wshadow -Werror -Wno-unused-result")

# mkbootimg
add_executable(mkbootimg src/mkbootimg.c)
set_property(TARGET mkbootimg PROPERTY INCLUDE_DIRECTORIES
	${PROJECT_SOURCE_DIR}/include
)
target_link_libraries(mkbootimg mincrypt)

# unpackbootimg
add_executable(unpackbootimg src/unpackbootimg.c)
set_property(TARGET unpackbootimg PROPERTY INCLUDE_DIRECTORIES
	${PROJECT_SOURCE_DIR}/include
)
target_link_libraries(unpackbootimg mincrypt)

# mincrypt
add_subdirectory(lib/libmincrypt)


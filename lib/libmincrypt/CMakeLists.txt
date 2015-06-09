# common
cmake_minimum_required(VERSION 2.8)
project(mincrypt)
set(CMAKE_BUILD_TYPE Release)

# common cflags
set(CMAKE_C_FLAGS "-Wall -Wextra -Wshadow -Werror -fPIC -static-libgcc -Wl,-static")

# sources
set(MINCRYPT_SOURCES
	dsa_sig.c p256.c p256_ec.c p256_ecdsa.c rsa.c sha.c sha256.c
)
add_library(mincrypt STATIC ${MINCRYPT_SOURCES})

# includes
set_property(TARGET mincrypt PROPERTY INCLUDE_DIRECTORIES
	${PROJECT_SOURCE_DIR}
	${PROJECT_SOURCE_DIR}/../../include
)

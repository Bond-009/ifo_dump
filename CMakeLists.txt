cmake_minimum_required(VERSION 3.1)
project(ifo_dump LANGUAGES C VERSION 1.0.0 DESCRIPTION "ifo_dump")

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_C_FLAGS "-std=c89 -Wall -Wextra -Wstrict-aliasing -pedantic -fstrict-aliasing")
set(CMAKE_C_FLAGS_DEBUG "-g")
set(CMAKE_C_FLAGS_RELEASE "-O3 -flto -s")

set(SOURCES ifo_dump.c)

# Add the executable
add_executable(ifo_dump ${SOURCES})
target_compile_options(ifo_dump PUBLIC)

# Include libdvdread
target_link_libraries(ifo_dump dvdread)

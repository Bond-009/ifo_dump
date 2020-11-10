cmake_minimum_required(VERSION 3.1)
project(ifo_dump LANGUAGES C VERSION 1.0.0 DESCRIPTION "ifo_dump")

set(SOURCES ifo_dump.c)

# Add the executable
add_executable(ifo_dump ${SOURCES})
target_compile_options(ifo_dump PUBLIC -std=c89 -Wall -Wextra -Weverything -Wstrict-aliasing -pedantic -fstrict-aliasing)

# Include libdvdread
target_link_libraries(ifo_dump dvdread)

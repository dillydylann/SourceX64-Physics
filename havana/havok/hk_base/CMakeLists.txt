# CMake script for the hk_base library

cmake_minimum_required(VERSION 3.16)
project(hk_base)

set(SRCDIR "${CMAKE_CURRENT_SOURCE_DIR}/../../../..")
set(CMAKE_MODULE_PATH "${SRCDIR}/cmake")

include(platform_dirs)
set(OUTLIBDIR "${LIBCOMMON}")

include(source_lib_base)

include_directories("${SRCDIR}/ivp/havana/havok" "${SRCDIR}/ivp/havana")
add_compile_definitions(VPHYSICS_EXPORTS HAVANA_CONSTRAINTS HAVOK_MOPP)


## Source Files ##

target_sources(${PROJECT_NAME}
    PRIVATE
        "array/array.cpp"
        "base_types.cpp"
        "console.cpp"
        "hash/hash.cpp"
        "id_server/id_server.cpp"
        "memory/memory.cpp"
        "memory/memory_util.cpp"
        "stopwatch/stopwatch.cpp"
        "string/string.cpp")

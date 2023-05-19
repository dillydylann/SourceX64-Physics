cmake_minimum_required(VERSION 3.16)
project(hk_math)

set(SRCDIR "${CMAKE_CURRENT_SOURCE_DIR}/../../../..")
set(CMAKE_MODULE_PATH "${SRCDIR}/cmake")

include(source_lib_base)

include_directories("${SRCDIR}/ivp/havana/havok" "${SRCDIR}/ivp/havana" "${SRCDIR}/ivp/ivp_utility")
add_compile_definitions(VPHYSICS_EXPORTS HAVANA_CONSTRAINTS HAVOK_MOPP)


## Source Files ##

target_sources(${PROJECT_NAME}
    PRIVATE
        "densematrix.cpp"
        "densematrix_util.cpp"
        "eulerangles.cpp"
        "gauss_elimination/gauss_elimination.cpp"
        "incr_lu/incr_lu.cpp"
        "lcp/lcp_solver.cpp"
        "math.cpp"
        "matrix3.cpp"
        "odesolve.cpp"
        "plane.cpp"
        "quaternion/quaternion.cpp"
        "quaternion/quaternion_util.cpp"
        "rotation.cpp"
        "spatial_matrix.cpp"
        "spatial_vector.cpp"
        "transform.cpp"
        "vector3/vector3.cpp"
        "vector3/vector3_util.cpp")


## Link Libraries ##

target_link_libraries(${PROJECT_NAME} hk_base)

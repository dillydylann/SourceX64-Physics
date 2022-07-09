# CMake script for the havana_constraints library

cmake_minimum_required(VERSION 3.16)
project(havana_constraints)

set(SRCDIR "${CMAKE_CURRENT_SOURCE_DIR}/../..")
set(CMAKE_MODULE_PATH "${SRCDIR}/cmake")

include(platform_dirs)
set(OUTLIBDIR "${LIBCOMMON}")

include(source_lib_base)

include_directories("${SRCDIR}/ivp/ivp_intern" "${SRCDIR}/ivp/ivp_collision" "${SRCDIR}/ivp/ivp_physics" "${SRCDIR}/ivp/ivp_surface_manager" "${SRCDIR}/ivp/ivp_utility" "${SRCDIR}/ivp/ivp_controller" "${SRCDIR}/ivp/ivp_compact_builder" "${SRCDIR}/ivp/havana/havok" "${SRCDIR}/ivp/havana")
add_compile_definitions(VPHYSICS_EXPORTS HAVANA_CONSTRAINTS HAVOK_MOPP IVP_VERSION_SDK)


## Source Files ##

target_sources(${PROJECT_NAME}
    PRIVATE
        "havok/hk_physics/constraint/ball_socket/ball_socket_constraint.cpp"
        "havok/hk_physics/constraint/breakable_constraint/breakable_constraint.cpp"
        "havok/hk_physics/constraint/constraint.cpp"
        "havok/hk_physics/constraint/fixed/fixed_constraint.cpp" 
        "havok/hk_physics/constraint/hinge/hinge_bp_builder.cpp"
        "havok/hk_physics/constraint/hinge/hinge_constraint.cpp"
        "havok/hk_physics/constraint/limited_ball_socket/limited_ball_socket_constraint.cpp"
        "havok/hk_physics/constraint/local_constraint_system/local_constraint_system.cpp"
        "havok/hk_physics/constraint/prismatic/prismatic_constraint.cpp"
        "havok/hk_physics/constraint/pulley/pulley_constraint.cpp"
        "havok/hk_physics/constraint/ragdoll/ragdoll_constraint.cpp"
        "havok/hk_physics/constraint/ragdoll/ragdoll_constraint_bp_builder.cpp"
        "havok/hk_physics/constraint/stiff_spring/stiff_spring_constraint.cpp"
        "havok/hk_physics/core/rigid_body_core.cpp"
        "havok/hk_physics/effector/rigid_body_binary_effector.cpp")
        

## Link Libraries ##

target_link_libraries(${PROJECT_NAME} hk_base hk_math)

cmake_minimum_required(VERSION 3.16)
project(ivp_compactbuilder)

set(SRCDIR "${CMAKE_CURRENT_SOURCE_DIR}/../..")
set(CMAKE_MODULE_PATH "${SRCDIR}/cmake")

include(source_lib_base)

include_directories("${SRCDIR}/ivp/ivp_intern" "${SRCDIR}/ivp/ivp_collision" "${SRCDIR}/ivp/ivp_physics" "${SRCDIR}/ivp/ivp_surface_manager" "${SRCDIR}/ivp/ivp_utility" "${SRCDIR}/ivp/ivp_controller" "${SRCDIR}/ivp/ivp_compact_builder" "${SRCDIR}/ivp/havana/havok" "${SRCDIR}/ivp/havana")
add_compile_definitions(IVP_VERSION_SDK HAVOK_MOPP)


## Source Files ##

target_sources(${PROJECT_NAME}
    PRIVATE
        "ivp_compact_ledge_gen.cxx"
        "3dsimport_co.cxx"
        "geompack_cutfac.cxx"
        "geompack_cvdec3.cxx"
        "geompack_drdec3.cxx"
        "geompack_dsphdc.cxx"
        "geompack_edght.cxx"
        "geompack_initcb.cxx"
        "geompack_insed3.cxx"
        "geompack_insfac.cxx"
        "geompack_insvr3.cxx"
        "geompack_prime.cxx"
        "geompack_ptpolg.cxx"
        "geompack_resedg.cxx"
        "ivp_compact_modify.cxx"
        "ivp_compact_recursive.cxx"
        "ivp_convex_decompositor.cxx"
        "ivp_halfspacesoup.cxx"
        "ivp_i_fpoint_vhash.cxx"
        "ivp_i_point_vhash.cxx"
        "ivp_object_polygon_tetra.cxx"
        "ivp_rot_inertia_solver.cxx"
        "ivp_surbuild_halfspacesoup.cxx"
        "ivp_surbuild_ledge_soup.cxx"
        "ivp_surbuild_pointsoup.cxx"
        "ivp_surbuild_polygon_convex.cxx"
        "ivp_surbuild_polyhdrn_cncv.cxx"
        "ivp_surbuild_q12.cxx"
        "ivp_templates_intern.cxx"
        "ivp_tetra_intrude.cxx"
        "ivv_cluster_min_hash.cxx"
        "qhull.cxx"
        "qhull_geom.cxx"
        "qhull_geom2.cxx"
        "qhull_global.cxx"
        "qhull_io.cxx"
        "qhull_mem.cxx"
        "qhull_merge.cxx"
        "qhull_poly.cxx"
        "qhull_poly2.cxx"
        "qhull_qset.cxx"
        "qhull_stat.cxx"
        "qhull_user.cxx")


## Link Libraries ##

target_link_libraries(${PROJECT_NAME} ivp_physics)
set(SRC
${CMAKE_CURRENT_SOURCE_DIR}/sh/default_image.cc
${CMAKE_CURRENT_SOURCE_DIR}/sh/default_image.h
${CMAKE_CURRENT_SOURCE_DIR}/sh/image.h
${CMAKE_CURRENT_SOURCE_DIR}/sh/spherical_harmonics.cc
${CMAKE_CURRENT_SOURCE_DIR}/sh/spherical_harmonics.h
)

add_library( spherical-harmonics STATIC ${SRC} )

target_link_libraries( spherical-harmonics eigen )

target_include_directories(spherical-harmonics  PRIVATE ./ )
target_include_directories(spherical-harmonics  PUBLIC ./ )

if ( X_PLATFORM_WINDOWS )
    target_compile_definitions( spherical-harmonics PUBLIC _USE_MATH_DEFINES )
endif()

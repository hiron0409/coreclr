set(CMAKE_INCLUDE_CURRENT_DIR ON)

if(PerfCountersSupportedBuild)
    add_definitions(-DENABLE_PERF_COUNTERS)
endif(PerfCountersSupportedBuild)

set(BCLTYPE_SOURCES
    arraynative.cpp
    arrayhelpers.cpp
    oavariant.cpp
    objectnative.cpp
    stringnative.cpp
    system.cpp
    varargsnative.cpp
    variant.cpp
)

if(CLR_CMAKE_PLATFORM_UNIX)
    add_compile_options(-fPIC)
endif(CLR_CMAKE_PLATFORM_UNIX)

add_library_clr(bcltype
    STATIC
    ${BCLTYPE_SOURCES}
)


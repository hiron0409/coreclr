include(${CLR_DIR}/crossgen.cmake)
include(../../md_wks.cmake)

add_precompiled_header(external.h ../external.cpp MDHOTDATA_SOURCES)

if (WIN32)
    list(APPEND MDHOTDATA_SOURCES ${MDHOTDATA_HEADERS})
endif (WIN32)

add_library_clr(mdhotdata_crossgen ${MDHOTDATA_SOURCES})

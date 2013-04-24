cmake_minimum_required (VERSION 2.8)

project (CFNetwork)

set (
    CMAKE_OSX_ARCHITECTURES
    "x86_64;i386"
)

set (
    CMAKE_C_FLAGS
    "${CMAKE_C_FLAGS} -Wall -Wno-deprecated-declarations"
)

set (
    CMAKE_CXX_FLAGS
    "${CMAKE_CXX_FLAGS} -Wall -Wno-deprecated-declarations"
)


set (
    INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/Headers
    ${CMAKE_CURRENT_SOURCE_DIR}/Dependencies/Headers
)

set (
    SOURCES
    CFNetwork.c
    cuEnc64.c
    JavaScriptGlue.c
    libresolv.c
    security_cdsa_utils.c
)

add_subdirectory (FTP)
add_subdirectory (Host)
add_subdirectory (HTTP)
add_subdirectory (NetDiagnostics)
add_subdirectory (NetServices)
add_subdirectory (Proxies)
add_subdirectory (SharedCode)
add_subdirectory (Stream)
add_subdirectory (URL)

include_directories (${INCLUDE_DIRECTORIES})

add_library (CFNetwork SHARED ${SOURCES})

target_link_libraries (
    CFNetwork
    "-framework CoreFoundation"
    "-framework Security"
    "-framework SystemConfiguration"
)

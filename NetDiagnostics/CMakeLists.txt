list (
    APPEND
    INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_SOURCE_DIR}
)

set (
    INCLUDE_DIRECTORIES
    "${INCLUDE_DIRECTORIES}"
    PARENT_SCOPE
)

list (
    APPEND
    SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/CFNetDiagnosticPing.c
    ${CMAKE_CURRENT_SOURCE_DIR}/CFNetDiagnostics.c
    ${CMAKE_CURRENT_SOURCE_DIR}/CFNetDiagnosticsProtocolUser.c
)

set (
    SOURCES
    "${SOURCES}"
    PARENT_SCOPE
)

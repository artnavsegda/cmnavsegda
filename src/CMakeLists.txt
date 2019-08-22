find_library(HELLO_LIB hello)
find_path(HELLO_INCLUDE_DIR hello.h)
include_directories(${HELLO_INCLUDE_DIR})

add_definitions(-DERROR_LOGSYSLOG)
add_definitions(-D_POSIX_C_SOURCE=200809L)
add_definitions(-D_XOPEN_SOURCE=700)

add_executable(cmhello
    cmhello.c
)

target_link_libraries(cmhello
  ${HELLO_LIB}
    pthread)

install(TARGETS cmhello
    RUNTIME DESTINATION bin)

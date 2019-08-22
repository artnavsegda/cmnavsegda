add_definitions(-DERROR_LOGSYSLOG)
add_definitions(-D_POSIX_C_SOURCE=200809L)
add_definitions(-D_XOPEN_SOURCE=700)

add_executable(cmhello
    cmhello.c
    gopt.c
)

target_link_libraries(cmhello
    pthread)

install(TARGETS cmhello
    RUNTIME DESTINATION bin)

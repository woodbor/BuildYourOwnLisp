cmake_minimum_required(VERSION 3.2)
project(byol)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -std=c99")
add_executable(byol ${SOURCE_FILES} s_expressions.c mpc.c)
target_link_libraries(byol -lm)
IF(${CMAKE_SYSTEM_NAME} MATCHES "Linux")
    target_link_libraries(s_expressions -ledit)
ENDIF(${CMAKE_SYSTEM_NAME} MATCHES "Linux")
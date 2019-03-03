project(tessellation LANGUAGES C)

file(COPY "tessellation.fs" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "tessellation.gs" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "tessellation.mat" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "tessellation.tcs" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "tessellation.tes" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "tessellation.vs" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/../../include
    )

file(GLOB PROJ_SRC *.c)

add_executable(${PROJECT_NAME} ${PROJ_SRC})

set_target_properties(${PROJECT_NAME} PROPERTIES PREFIX "")
target_link_libraries(${PROJECT_NAME} corange GL SDL2 SDL2_net SDL2_mixer m)


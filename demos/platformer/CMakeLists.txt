project(platformer LANGUAGES C)

file(COPY "backgrounds" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "levels" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "sounds" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY "tiles" DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}/../../include
    )

file(GLOB PROJ_SRC src/*.c)

add_executable(${PROJECT_NAME} ${PROJ_SRC})

set_target_properties(${PROJECT_NAME} PROPERTIES PREFIX "")
target_link_libraries(${PROJECT_NAME} corange GL SDL2 SDL2_net SDL2_mixer m)


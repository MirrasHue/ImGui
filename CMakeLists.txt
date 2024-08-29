cmake_minimum_required(VERSION 3.20)

project(ImGui)

# Fetch source files
file(GLOB_RECURSE imgui_src CONFIGURE_DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)

add_library(${PROJECT_NAME} STATIC ${imgui_src})

target_include_directories(${PROJECT_NAME}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/include/imgui # So that internal ImGui includes don't brake
        ${CMAKE_CURRENT_SOURCE_DIR}/include/imgui/backends # Same, just for not braking include paths
        ${CMAKE_SOURCE_DIR}/MirrasENGINE/3rdParty/GLFW/include
)
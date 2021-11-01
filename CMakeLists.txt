cmake_minimum_required(VERSION 3.20)
project(FragmentRenderingOrder)

set(CMAKE_CXX_STANDARD 14)

# GLFW3
option(GLFW_BUILD_DOCS OFF)
option(GLFW_BUILD_EXAMPLES OFF)
option(GLFW_BUILD_TESTS OFF)
add_subdirectory(3rd_party/glfw)

# glad
set(GLAD_FILES 3rd_party/glad/src/glad.c)

# imgui
file(GLOB IMGUI_FILES 3rd_party/imgui/*.cpp)

# INCLUDE
include_directories(
    3rd_party/glad/include
    3rd_party/glfw/include
    3rd_party/Nuklear
    3rd_party/imgui
)

add_executable(FragmentRenderingOrder main.cpp ${GLAD_FILES} ${IMGUI_FILES})
target_link_libraries(FragmentRenderingOrder glfw)

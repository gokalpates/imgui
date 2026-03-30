cmake_minimum_required(VERSION 3.20)

project(imgui VERSION 0.0.1)

add_library(imgui STATIC
    "imgui.cpp"
    "imgui_demo.cpp"
    "imgui_draw.cpp"
    "backends/imgui_impl_glfw.cpp"
    "backends/imgui_impl_vulkan.cpp"
    "imgui_tables.cpp"
    "imgui_widgets.cpp"
)

target_compile_definitions(imgui PUBLIC IMGUI_IMPL_VULKAN_USE_VOLK)

target_include_directories(imgui PUBLIC 
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/backends
)

target_link_libraries(imgui PUBLIC volk glfw)

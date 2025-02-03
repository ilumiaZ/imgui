# third_party/imgui/CMakeLists.txt
add_library(imgui STATIC
    imgui.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    backends/imgui_impl_glfw.cpp
    backends/imgui_impl_vulkan.cpp
)

# 添加头文件路径
target_include_directories(imgui PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/backends
)

# 声明依赖库
target_link_libraries(imgui PRIVATE
    glfw                           # GLFW库目标
    Vulkan::Vulkan                 # Vulkan库目标
)
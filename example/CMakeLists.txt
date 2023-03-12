
link_libraries(nanovg)

find_package(GLEW)


if (NOT USE_SYSTEM_GLFW)
    find_package(glfw3)
endif()

link_libraries(GLEW::GLEW glfw)

add_definitions(-DNANOVG_GLEW)

add_executable(example_gles3 WIN32 example_gles3.c demo.c perf.c)

add_executable(example_gles2 WIN32 example_gles2.c demo.c perf.c)


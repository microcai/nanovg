
link_libraries(nanovg)

if (NOT USE_SYSTEM_GLFW)
    find_package(glfw3)
endif()

link_libraries(glfw)

set(demo_SRC demo.c perf.c)

add_executable(example_gl2 WIN32 example_gl2.c ${demo_SRC})
add_executable(example_gl3 WIN32 example_gl3.c ${demo_SRC})
add_executable(example_fbo WIN32 example_fbo.c ${demo_SRC})

#link_libraries(GLEW::GLEW)
#add_definitions(-DNANOVG_GLEW)

add_executable(example_gles3 WIN32 example_gles3.c ${demo_SRC})

add_executable(example_gles2 WIN32 example_gles2.c ${demo_SRC})


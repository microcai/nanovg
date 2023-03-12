cmake_minimum_required(VERSION 3.18 FATAL_ERROR)

project(GLEW VERSION 3.3.8 LANGUAGES C)

add_library(glew_static STATIC src/glew.c)

target_link_libraries(glew_static OpenGL::EGL)

target_compile_definitions(glew_static PRIVATE -DGLEW_NO_GLU -DGLEW_STATIC)

if (NOT WIN32)
    target_link_libraries(glew_static OpenGL::GLX)
endif()

add_library(GLEW::GLEW ALIAS glew_static)



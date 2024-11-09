cmake_minimum_required(VERSION 3.28)

project(Engine  VERSION 0.1
                DESCRIPTION "Game Engine for strategies"
                LANGUAGES CXX)

add_library(renderer STATIC src/renderer.cpp include/renderer.h)
target_include_directories(renderer PUBLIC include include/vulkan)
target_compile_features(renderer PUBLIC cxx_std_23)


add_executable(engine main.cpp)
target_link_libraries(engine PUBLIC renderer)   # link engine against renderer
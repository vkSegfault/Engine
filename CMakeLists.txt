cmake_minimum_required(VERSION 3.28)

project(Engine  VERSION 0.1
                DESCRIPTION "Game Engine for strategies"
                LANGUAGES CXX)



# in the Cherno engine series Engine is actually dll and game is exe that uses engine dll to work

add_library(renderer STATIC src/renderer.cpp include/renderer.h)
target_include_directories(renderer PUBLIC include include/vulkan)
target_compile_features(renderer PUBLIC cxx_std_23)


add_executable(engine main.cpp)
target_link_libraries(engine PUBLIC renderer)   # link engine against renderer

set_target_properties(engine PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")
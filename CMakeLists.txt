cmake_minimum_required(VERSION 3.15)

# Project definition
project(rlImGui LANGUAGES CXX)

# Define the static library with rlImGui source files
add_library(rlImGui STATIC
    rlImGui.cpp
)

# Set include directories for rlImGui.h and imgui_impl_raylib.h
target_include_directories(rlImGui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# Link against raylib and imgui, assuming they are defined as targets elsewhere
# We use PUBLIC here so that any target linking against rlImGui
# automatically gets the necessary includes and links for imgui and raylib.
target_link_libraries(rlImGui PUBLIC raylib imgui)

# Ensure C++11 standard for compatibility
target_compile_features(rlImGui PUBLIC cxx_std_11)

message(STATUS "Configured rlImGui library")
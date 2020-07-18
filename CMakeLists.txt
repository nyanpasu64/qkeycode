cmake_minimum_required(VERSION 3.12)

project(qkeycode LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt5 COMPONENTS Gui Widgets REQUIRED)

add_library(qkeycode STATIC
    src/qkeycode/qkeycode.cpp
    src/qkeycode/chromium/keycode_converter.cc
)
target_include_directories(qkeycode
    PUBLIC include
    PRIVATE src
)
target_link_libraries(qkeycode PRIVATE Qt5::Gui)

target_compile_definitions(qkeycode PRIVATE KEYCODEQT_LIBRARY)

cmake_minimum_required(VERSION 3.21)

project(hello-wxWidgets LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(wxBUILD_SHARED OFF)
set(wxBUILD_COMPATIBILITY "3.1")
add_subdirectory(external/wxWidgets)

add_executable(hello-wxWidgets
    main.cpp
)
target_include_directories(hello-wxWidgets PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/external/wxWidgets/include")
target_link_libraries(hello-wxWidgets wx::net wx::core wx::base)

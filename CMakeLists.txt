cmake_minimum_required(VERSION 3.28)
project(skakspil_gui LANGUAGES CXX)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

include(FetchContent)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 3.0.2
    GIT_SHALLOW ON
    EXCLUDE_FROM_ALL
    SYSTEM)
FetchContent_MakeAvailable(SFML)

add_executable(skakspil_gui src/gui/main_gui.cpp)
target_compile_features(skakspil_gui PRIVATE cxx_std_17)
target_link_libraries(skakspil_gui PRIVATE SFML::Graphics)
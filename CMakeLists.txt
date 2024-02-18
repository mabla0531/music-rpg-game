cmake_minimum_required(VERSION 3.22.1)
project(music_rpg)


set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
option(BUILD_SHARED_LIBS "Build shared libraries" OFF)

include(FetchContent)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 2.6.x)
FetchContent_MakeAvailable(SFML)

add_executable(music_rpg 
    src/main.cpp 
    src/other.cpp
)

target_link_libraries(music_rpg PRIVATE sfml-graphics)
target_compile_features(music_rpg PRIVATE cxx_std_17)

install(TARGETS music_rpg)
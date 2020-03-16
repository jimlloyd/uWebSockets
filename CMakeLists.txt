cmake_minimum_required (VERSION 3.10.2)

project (uWebSockets)

find_program(CMAKE_C_COMPILER gcc)
find_program(CMAKE_CXX_COMPILER g++)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(uSockets)

add_library(uWebSockets INTERFACE)

target_include_directories(uWebSockets INTERFACE src)
target_link_libraries(uWebSockets INTERFACE uSockets)

# TODO: use CMake OPTIONs
target_compile_definitions(uWebSockets INTERFACE LIBUS_NO_SSL)
target_compile_definitions(uWebSockets INTERFACE UWS_NO_ZLIB)

# For now, use libuv because because it isolates the underlying platform and is fast
target_compile_definitions(uWebSockets INTERFACE WITH_LIBUV)

add_subdirectory(examples)

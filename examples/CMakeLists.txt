

add_executable(BroadcastingEchoServer BroadcastingEchoServer.cpp)
target_link_libraries(BroadcastingEchoServer uWebSockets)

add_executable(EchoServer EchoServer.cpp)
target_link_libraries(EchoServer uWebSockets)

add_executable(EchoServerThreaded EchoServerThreaded.cpp)
target_link_libraries(EchoServerThreaded uWebSockets)

add_executable(HelloWorld HelloWorld.cpp)
target_link_libraries(HelloWorld uWebSockets)

add_executable(HelloWorldThreaded HelloWorldThreaded.cpp)
target_link_libraries(HelloWorldThreaded uWebSockets)

# Disabled because <filesystem> is not available with Apple clang 10 and I am too lazy to figure out a workaround
# https://stackoverflow.com/questions/42633477/macos-clang-c17-filesystem-header-not-found
# add_executable(HttpServer HttpServer.cpp)
# target_link_libraries(HttpServer uWebSockets)

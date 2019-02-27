cmake_minimum_required(VERSION 3.0.0)
project(sfml_hello_world VERSION 0.1.0)

add_executable(sfml_hello_world main.cpp)

find_package(SFML 2 COMPONENTS network audio graphics window system REQUIRED)
target_link_libraries(sfml_hello_world PRIVATE X11 FLAC UDev OpenAL)
if(SFML_FOUND)
  message("sfml found")
  target_link_libraries(sfml_hello_world PUBLIC sfml-graphics sfml-network sfml-audio sfml-window sfml-system)
endif()
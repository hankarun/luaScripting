cmake_minimum_required(VERSION 3.18)
project(game
  LANGUAGES C CXX
  VERSION 1.0
)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

add_subdirectory(third_party)
add_subdirectory(src)

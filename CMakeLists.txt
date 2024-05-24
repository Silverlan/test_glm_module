cmake_minimum_required(VERSION 3.28)

set(PROJ_NAME glm_test)
project(${PROJ_NAME} CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

add_subdirectory(glm_cxxmodule)

add_executable(${PROJ_NAME})
add_dependencies(${PROJ_NAME} glm_module)

target_sources(${PROJ_NAME}
  PRIVATE main.cpp
)

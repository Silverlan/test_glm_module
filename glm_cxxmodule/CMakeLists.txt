cmake_minimum_required(VERSION 3.28)

set(PROJ_NAME glm_module)
project(${PROJ_NAME} CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

add_definitions(-DGLM_FORCE_DEPTH_ZERO_TO_ONE)
add_definitions(-DGLM_ENABLE_EXPERIMENTAL)
add_definitions(-DGLM_FORCE_CTOR_INIT)
add_definitions(-DGLM_ENABLE_CXX_20)

add_library(${PROJ_NAME} STATIC)
target_include_directories(${PROJ_NAME} PRIVATE "${CMAKE_CURRENT_LIST_DIR}/glm/")
target_sources(${PROJ_NAME}
  PUBLIC
    FILE_SET cxx_modules TYPE CXX_MODULES FILES
    glm/glm/glm.cppm
)

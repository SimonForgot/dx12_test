cmake_minimum_required(VERSION 3.23)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

get_filename_component(ProjectId ${CMAKE_CURRENT_SOURCE_DIR} NAME)
string(REPLACE " " "_" ProjectId ${ProjectId})
project(${ProjectId} LANGUAGES CXX)

find_package(glm REQUIRED)

add_executable(${ProjectId} WIN32 main.cpp)
target_link_libraries(${ProjectId}  PRIVATE  glm::glm)

add_custom_target(run COMMAND $<TARGET_FILE:${ProjectId}>)

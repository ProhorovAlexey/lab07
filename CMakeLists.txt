cmake_minimum_required(VERSION 3.16)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include("cmake/HunterGate.cmake")

HunterGate(
        URL "https://github.com/ProhorovAlexey/hunter/archive/my_tag.tar.gz"
        SHA1 "7fb02e15587784811a853f997ccad9a996aaa381"
)

project(project)

hunter_add_package(print)
find_package(print)

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} print)

install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION bin)

cmake_minimum_required(VERSION 3.0.0)
project(splitsprite VERSION 0.1.0)

include("cmake/CPM.cmake")


set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)


set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_CXX_EXTENSIONS ON)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g -Wextra")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -O3")

include(CTest)
enable_testing()

#CPMAddPackage("gh:daancode/a-star#master")
# CPMAddPackage(
#     NAME astar
#     GIT_TAG master
#     GITHUB_REPOSITORY "daancode/a-star"
#     # Eigen's CMakelists are not intended for library use
#     DOWNLOAD_ONLY YES 
# )

find_package(fmt)

add_executable(splitsprite src/splitsprite.cpp)
target_link_libraries(splitsprite PUBLIC fmt::fmt)

cmake_minimum_required(VERSION "3.12")
project("sidemade")

# Make cmake modules visible to CMake
list (APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake")

find_package(Eigen3 3.2 REQUIRED)
find_package(yaml-cpp 0.6.0 REQUIRED)

file(GLOB_RECURSE SRC_FILES CONFIGURE_DEPENDS src/*.cpp)

add_executable("${PROJECT_NAME}" "${SRC_FILES}")

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 11)

target_link_libraries("${PROJECT_NAME}" PRIVATE Eigen3::Eigen yaml-cpp)

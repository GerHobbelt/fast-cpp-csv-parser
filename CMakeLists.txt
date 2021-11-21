cmake_minimum_required(VERSION 3.12)
project("fast-cpp-csv-parser" VERSION 1.0.0
  DESCRIPTION "Header-only library for C++11 to parse (read) CSV files"
  HOMEPAGE_URL "https://github.com/CodeFinder2/fast-cpp-csv-parser")
include(GNUInstallDirs)

add_library(${PROJECT_NAME} INTERFACE)
target_include_directories(
  ${PROJECT_NAME}
  INTERFACE $<BUILD_INTERFACE:${${PROJECT_NAME}_SOURCE_DIR}/include>
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)
target_compile_features(${PROJECT_NAME} INTERFACE cxx_std_11)

install(DIRECTORY ${PROJECT_SOURCE_DIR}/include/${PROJECT_NAME} DESTINATION include)

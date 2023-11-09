cmake_minimum_required(VERSION 3.19)

project(boost-template)

include(FetchContent)

FetchContent_Declare(
  Boost
  URL https://github.com/boostorg/boost/releases/download/boost-1.83.0/boost-1.83.0.tar.xz
  TLS_VERIFY TRUE
  DOWNLOAD_EXTRACT_TIMESTAMP ON
)

FetchContent_MakeAvailable(Boost)

#if(NOT Boost_POPULATED)

#  message(STATUS "Fetching Boost")
#  FetchContent_Populate(Boost)

#  message(STATUS "Configuring Boost")
#  add_subdirectory(${Boost_SOURCE_DIR} ${Boost_BINARY_DIR} EXCLUDE_FROM_ALL)

#endif()

include_directories(${Boost_INCLUDE_DIR})
add_executable(boost-example src/main.cpp)


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

add_executable(boost-example src/main.cpp)

target_link_libraries(boost-example PRIVATE Boost::lambda)

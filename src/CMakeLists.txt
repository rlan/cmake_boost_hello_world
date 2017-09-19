cmake_minimum_required (VERSION 3.1)
project (Hello)

set (CMAKE_CXX_STANDARD 11)

find_package(Boost 1.48.0 REQUIRED COMPONENTS
             date_time filesystem program_options)
if (Boost_FOUND)
  include_directories("${Boost_INCLUDE_DIRS}" "${PROJECT_SOURCE_DIR}")

  add_executable(Hello main.cc)
  target_link_libraries(Hello ${Boost_LIBRARIES})
endif()

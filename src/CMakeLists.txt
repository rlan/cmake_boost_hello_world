cmake_minimum_required (VERSION 2.8)
project (Hello)

find_package(Boost 1.48.0 REQUIRED COMPONENTS
             date_time filesystem program_options)
if (Boost_FOUND)
  include_directories("${Boost_INCLUDE_DIRS}" "${PROJECT_BINARY_DIR}")

  # add the executable
  add_executable(Hello main.cc)
  target_link_libraries(Hello ${Boost_LIBRARIES})
endif()

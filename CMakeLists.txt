cmake_minimum_required(VERSION 3.4)

project(GSL VERSION 1.0.0 LANGUAGES CXX)

set(GSL_HEADERS
    "include/gsl/gsl"
    "include/gsl/gsl_assert"
    "include/gsl/gsl_byte"
    "include/gsl/gsl_util"
    "include/gsl/multi_span"
    "include/gsl/span"
    "include/gsl/string_span"
)

add_library(gsl INTERFACE)
target_include_directories(gsl INTERFACE include)

include_directories(
    ${CMAKE_CURRENT_BINARY_DIR}
    include
)

install(FILES ${GSL_HEADERS}
    DESTINATION include/gsl
)

enable_testing()

add_subdirectory(tests)


cmake_minimum_required( VERSION 3.5 )

project( hexxlt )

set( CMAKE_POSITION_INDEPENDENT_CODE ON )

# Make external libraries globally available.
include( external/boost/CMakeLists.txt )

add_subdirectory( app )

set( CMAKE_CXX_STANDARD 17 )

set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

include( CheckCXXCompilerFlag )
CHECK_CXX_COMPILER_FLAG( "-march=native" COMPILER_SUPPORTS_MARCH_NATIVE )
if( COMPILER_SUPPORTS_MARCH_NATIVE )
    set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -march=native" )
endif()


add_library( hexxlt "src/dummy.cpp" )
target_sources( hexxlt PRIVATE
  "src/hexxlt.cpp"
)

#add_executable( cli "src/dummy.cpp" )
#target_sources( cli PRIVATE
#  "src/main.cpp"
#)

include_directories( "src" )
include_directories( ${Boost_INCLUDE_DIR} )

#target_link_libraries( cli hexxlt )

# Unit tests
add_executable( utests "src/dummy.cpp" )
target_sources( utests PRIVATE
  "src/utest/main.cpp"
)

target_link_libraries( utests hexxlt )

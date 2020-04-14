# ./external/boost/CMakeLists.txt -- Traditional CMake

set( BOOST_VERSION 1.72 )

# Settings for finding correct Boost libraries.
set( Boost_USE_STATIC_LIBS      FALSE )
set( Boost_USE_MULTITHREADED    FALSE )
set( Boost_USE_STATIC_RUNTIME   FALSE )
set( Boost_ADDITIONAL_VERSIONS  "${BOOST_VERSION}" )
set( Boost_COMPILER             "-gcc" )

# Search for Boost libraries.
set( BOOST_ROOT ${CMAKE_CURRENT_LIST_DIR} )
find_package( Boost
  ${BOOST_VERSION} EXACT
  REQUIRED
#  COMPONENTS
#    system
)

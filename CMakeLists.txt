# ======================================================================
#  larreco main build file
#
#  cd .../path/to/build/directory
#  source .../path/to/larreco/ups/setup_for_development <-d|-p>
#  buildtool [-I /install/path] -bt[i] -jN
# ======================================================================

cmake_minimum_required(VERSION 3.19 FATAL_ERROR)

project(larreco VERSION 09.06.12.01 LANGUAGES CXX)

set(larreco_FW_DIR fw)

find_package(cetmodules REQUIRED)
find_package(canvas_root_io)
find_package(art)

include(CetCMakeEnv)
cet_cmake_env()

cet_set_compiler_flags(DIAGS CAUTIOUS
  WERROR
  NO_UNDEFINED
  EXTRA_FLAGS -pedantic -Wno-unused-local-typedefs
)

cet_report_compiler_flags()

# these are minimum required versions, not the actual product versions
find_package( Eigen3 )
find_package( larcoreobj )
find_package( larcorealg )
find_package( larcore )
find_package( lardataobj )
find_package( lardataalg )
find_package( lardata )
find_package( larevt )
find_package( larsim )
find_package( nutools )
find_package( nug4 )
find_package( nurandom )
find_package( nusimdata )
find_package( art )
find_package(art_root_io)
find_package(messagefacility)
find_package(cetlib_except)
find_package( PostgreSQL )
find_package( RangeV3 )
find_package( ROOT )
find_package( Geant4 )
find_package( CLHEP COMPONENTS Random REQUIRED)
# macros for dictionary and simple_plugin
include(ArtDictionary)
include(ArtMake)
include(BuildPlugins)

include_directories( ${EIGEN3_INCLUDE_DIRS} )

# source
add_subdirectory(larreco)

# tests
add_subdirectory(test)
add_subdirectory(cmakeConfig)
# ups - table and config files
if(WANT_UPS)
add_subdirectory(ups)
endif()

# packaging utility
#include(UseCPack)

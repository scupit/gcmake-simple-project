################################################################################
# Generated with Skylar Cupit's json-to-cmake tool                             #
# GitHub: https://github.com/scupit/json-to-cmake-rewrite                      #
################################################################################

cmake_minimum_required( VERSION 3.12 )
project( gcmake-simple-project )

# ////////////////////////////////////////////////////////////////////////////////
# LANGUAGE STANDARDS
# ////////////////////////////////////////////////////////////////////////////////

set( CMAKE_C_STANDARD 99 CACHE STRING "C compiler standard year" )
set_property( CACHE CMAKE_C_STANDARD PROPERTY STRINGS 99 )
message( "Using C compiler standard --std=c${CMAKE_C_STANDARD}" )

set( CMAKE_CXX_STANDARD 11 CACHE STRING "CXX compiler standard year" )
set_property( CACHE CMAKE_CXX_STANDARD PROPERTY STRINGS 11 )
message( "Using CXX compiler standard --std=c++${CMAKE_CXX_STANDARD}" )

set( CMAKE_C_STANDARD_REQUIRED ON )
set( CMAKE_CXX_STANDARD_REQUIRED ON )

set( CMAKE_C_EXTENSIONS OFF )
set( CMAKE_CXX_EXTENSIONS OFF )

# ////////////////////////////////////////////////////////////////////////////////
# BUILD TARGETS
# ////////////////////////////////////////////////////////////////////////////////

set_property( CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS "Debug" "Release" )

if( "${CMAKE_BUILD_TYPE}" STREQUAL "" )
	set( CMAKE_BUILD_TYPE "Debug" CACHE STRING "Project Configuration" FORCE )
endif()

if( "${CMAKE_BUILD_TYPE}" STREQUAL "Debug" )
	set( CMAKE_CXX_FLAGS "-g -Wall -Wextra -Wconversion -Wuninitialized -pedantic -pedantic-errors " )
	set( CMAKE_C_FLAGS "-g -Wall -Wextra -Wconversion -Wuninitialized -pedantic -pedantic-errors " )
elseif( "${CMAKE_BUILD_TYPE}" STREQUAL "Release" )
	set( CMAKE_CXX_FLAGS "-O2 -DNDEBUG -s " )
	set( CMAKE_C_FLAGS "-O2 -DNDEBUG -s " )
endif()

message( "Using compiler flags: ${CMAKE_CXX_FLAGS}" )
message( "Building project '${CMAKE_BUILD_TYPE}' configuration" )

# ////////////////////////////////////////////////////////////////////////////////
# IMPORTED LIBRARIES (none)
# ////////////////////////////////////////////////////////////////////////////////

# ////////////////////////////////////////////////////////////////////////////////
# OUTPUT SHARED LIBRARIES (none)
# ////////////////////////////////////////////////////////////////////////////////

# ////////////////////////////////////////////////////////////////////////////////
# OUTPUT STATIC LIBRARIES (none)
# ////////////////////////////////////////////////////////////////////////////////

# ////////////////////////////////////////////////////////////////////////////////
# LIBRARY OUTPUT GROUPS (none)
# ////////////////////////////////////////////////////////////////////////////////

# ////////////////////////////////////////////////////////////////////////////////
# EXECUTABLE OUTPUT GROUPS (none)
# ////////////////////////////////////////////////////////////////////////////////

# ////////////////////////////////////////////////////////////////////////////////
# OUTPUT EXECUTABLES 
# ////////////////////////////////////////////////////////////////////////////////

# Output executable: run-project
set( run-project_HEADERS
	${PROJECT_SOURCE_DIR}/include/Printer.hpp
)

set( run-project_SOURCES
	${run-project_HEADERS}
	${PROJECT_SOURCE_DIR}/main.cpp
	${PROJECT_SOURCE_DIR}/src/Printer.cpp
)

set( run-project_INCLUDE_DIRS
	${PROJECT_SOURCE_DIR}/include
)

add_executable( run-project ${run-project_SOURCES} )
target_include_directories( run-project PRIVATE ${run-project_INCLUDE_DIRS} )

set_target_properties( run-project PROPERTIES
	RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/${CMAKE_BUILD_TYPE}
)

# ////////////////////////////////////////////////////////////////////////////////
# LINK LIBRARIES TO OUTPUTS
# ////////////////////////////////////////////////////////////////////////////////


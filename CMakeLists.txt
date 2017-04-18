# Minimum cmake version
CMAKE_MINIMUM_REQUIRED(VERSION 3.5)

# Name of the project
PROJECT(omega)

# Version of the project
SET(omega_VERSION_MAJOR 0)
SET(omega_VERSION_MINOR 91)

# Location of the custom cmake modules
SET(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

# Quick & Dirty hack
ADD_DEFINITIONS(-DBSD)

# Compilation
SET (CMAKE_C_FLAGS       "-Weverything")
SET (CMAKE_C_FLAGS_DEBUG "-g")

ADD_COMPILE_OPTIONS(${CMAKE_C_FLAGS})

INCLUDE(CheckLibraryExists)

FIND_PACKAGE(Curses REQUIRED)
INCLUDE_DIRECTORIES(SYSTEM ${CURSES_INCLUDE_DIR})

ADD_SUBDIRECTORY(tools)
ADD_SUBDIRECTORY(src)

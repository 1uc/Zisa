cmake_minimum_required(VERSION 3.14 FATAL_ERROR)
project(Zisa LANGUAGES C CXX)

set(as_subproject ZisaCore ZisaMemory ZisaMPI ZisaSFC ZisaFVM ZisaTimeStepping)

macro(find_package)
  if(NOT "${ARGV0}" IN_LIST as_subproject)
    _find_package(${ARGV})
  endif()
endmacro()

enable_testing()

add_subdirectory(core)
add_subdirectory(memory)
add_subdirectory(mpi)
add_subdirectory(sfc)
add_subdirectory(time_stepping)
add_subdirectory(fvm)

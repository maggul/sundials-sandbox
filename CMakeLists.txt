cmake_minimum_required (VERSION 3.10)
project (SUNDIALS-Sandbox)

find_package(SUNDIALS REQUIRED)

# To add an executable:
# * use the "add_executable" command, that lists the executable
#   name, followed by all source files that contribute to that
#   executable.
# * use the "target_link_libraries" command, that repeats the
#   executable name, followed by the list of libraries (from
#   SUNDIALS and elsewhere) that the executable depends on.
#
# Multiple examples of this are below, that create targets for
# each executable.  Note that each of these link against a target
# provided by SUNDIALS (information on the available targets may
# be found in the SUNDIALS documentation,
# https://sundials.readthedocs.io/en/latest/sundials/Install_link.html#using-sundials-as-a-third-party-library-in-other-cmake-projects)
# as well as the standard math library, "libm".

add_executable(testComplexNVector
  testComplexNVector.c
  nvector_serialcomplex.c)
target_link_libraries(testComplexNVector PUBLIC
  SUNDIALS::core
  m)

add_executable(test_SPTFQRM
  test_SPTFQRM.c
  sunlinsol_sptfqmrcomplex.c
  nvector_serialcomplex.c)
target_link_libraries(test_SPTFQRM PUBLIC
  SUNDIALS::core
  m)

add_executable(test_PCG
test_PCG.c
  sunlinsol_pcgcomplex.c
  nvector_serialcomplex.c)
target_link_libraries(test_PCG PUBLIC
  SUNDIALS::core
  m)

add_executable(complex_ark_extended
  complex_ark_extended.c)
target_link_libraries(complex_ark_extended PUBLIC
  SUNDIALS::arkode
  m)

  add_executable(complex_erk_extended
  complex_erk_extended.c)
target_link_libraries(complex_erk_extended PUBLIC
  SUNDIALS::arkode
  m)

  add_executable(complex_ark_extended_system
  complex_ark_extended_system.c)
target_link_libraries(complex_ark_extended_system PUBLIC
  SUNDIALS::arkode
  m)

  add_executable(complex_erk_NVector_serial_complex
  complex_erk_NVector_serial_complex.c
  nvector_serialcomplex.c)
target_link_libraries(complex_erk_NVector_serial_complex PUBLIC
  SUNDIALS::arkode
  m)

  add_executable(complex_IMEX
  complex_IMEX.c
  nvector_serialcomplex.c
  sunlinsol_sptfqmrcomplex.c)
target_link_libraries(complex_IMEX PUBLIC
  SUNDIALS::arkode
  m)

  add_executable(complex_CVODE
  complex_CVODE.c
  nvector_serialcomplex.c
  sunlinsol_sptfqmrcomplex.c)
target_link_libraries(complex_CVODE PUBLIC
  SUNDIALS::cvode
  m)
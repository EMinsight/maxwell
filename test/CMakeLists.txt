cmake_minimum_required(VERSION 3.0)

find_package(GTest CONFIG REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})

find_package(mfem CONFIG REQUIRED)
include_directories(${MFEM_INCLUDE_DIRS})

find_package(Boost 1.78.0 REQUIRED)
include_directories(${Boost_INCLUDE_DIRS})

include_directories(${maxwell_solvers_INCLUDE_DIRS})

add_executable(maxwell_tests 
"TestAux.cpp" 
"maxwell/TestSolver.cpp" 
"maxwell/TestBilinearIntegrators.cpp" 
"maxwell/TestMaterial.cpp" "maxwell/TestProbes.cpp" "maxwell/TestSources.cpp")

target_link_libraries(maxwell_tests maxwell_solvers GTest::gtest GTest::gtest_main Boost::boost) 



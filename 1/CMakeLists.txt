cmake_minimum_required(VERSION 3.10)
project(1)

find_package(LLVM)

message(STATUS "Found LLVM ${LLVM_PACKAGE_VERSION}")
message(STATUS "Using LLVMConfig.cmake in: ${LLVM_DIR}")

include_directories(${LLVM_INCLUDE_DIRS})
separate_arguments(LLVM_DEFINITIONS_LIST NATIVE_COMMAND ${LLVM_DEFINITIONS})
add_definitions(${LLVM_DEFINITIONS_LIST})

add_executable(main main.cpp)

llvm_map_components_to_libnames(llvm_libs support core irreader)

target_link_libraries(main PUBLIC ${llvm_libs})

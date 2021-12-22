cmake_minimum_required(VERSION 3.10)
project(1)

add_subdirectory(llvm-project/llvm)

add_executable(main main.cpp)

llvm_map_components_to_libnames(llvm_libs support core irreader)

target_link_libraries(main PUBLIC ${llvm_libs})
target_include_directories(main PUBLIC "${PROJECT_BINARY_DIR}/llvm-project/llvm/include" "${PROJECT_SOURCE_DIR}/llvm-project/llvm/include")

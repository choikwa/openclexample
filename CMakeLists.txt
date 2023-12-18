cmake_minimum_required(VERSION 3.1) # 3.1 << C_STANDARD 11

project(HelloOpenCL LANGUAGES C)

find_package(OpenCL REQUIRED)

INCLUDE_DIRECTORIES(${OpenCL_INCLUDE_DIRS}) 

LINK_DIRECTORIES(${OpenCL_LIBRARY})

add_executable(${PROJECT_NAME} Main.c)

configure_file(vector_add_kernel.cl vector_add_kernel.cl COPYONLY)

target_link_libraries(${PROJECT_NAME} PRIVATE OpenCL::OpenCL)

set_target_properties(${PROJECT_NAME} PROPERTIES C_STANDARD 11
                                                 C_STANDARD_REQUIRED ON
                                                 C_EXTENSIONS OFF)

target_compile_definitions(${PROJECT_NAME} PRIVATE CL_TARGET_OPENCL_VERSION=100)
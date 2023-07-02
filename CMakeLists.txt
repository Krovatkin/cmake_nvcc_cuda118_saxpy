cmake_minimum_required(VERSION 3.12)
project(cuda_program)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CUDA_STANDARD 17)

# w/o this line CMake can't find some CUDA libs e.g.
# """
# Could NOT find CUDA (missing: CUDA_INCLUDE_DIRS CUDA_CUDART_LIBRARY) (found
#  version "11.8")
# """
set(CUDA_TOOLKIT_ROOT_DIR "/home/villedepommes/Downloads/cuda-11.8")
# Find CUDA
find_package(CUDA REQUIRED)

# Set CUDA architectures (change according to your GPU architecture)
#set(CUDA_ARCHITECTURES 61)

# Add CUDA executable
cuda_add_executable(cuda_program main.cu)

# Link CUDA libraries
target_link_libraries(cuda_program ${CUDA_LIBRARIES})


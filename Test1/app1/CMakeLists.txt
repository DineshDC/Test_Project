cmake_minimum_required(VERSION 3.5.0)
set(PROJECT_NAME app1)
project (${PROJECT_NAME})

SET(CMAKE_SYSTEM_NAME Linux)
#this one not so much
SET(CMAKE_SYSTEM_VERSION 1)

# specify the cross compiler
SET(CMAKE_C_COMPILER   gcc)
SET(CMAKE_CXX_COMPILER g++)

# where is the target environment 
#SET(CMAKE_FIND_ROOT_PATH  /ssp-linux/a6n2/sdk/)

# search for programs in the build host directories
SET(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
# for libraries and headers in the target directories
SET(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
SET(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)


#However, the file(GLOB...) allows for wildcard additions:
file(GLOB SOURCES "*.cpp")

#Store executable to the specific path
set(EXECUTABLE_OUTPUT_PATH "../../bins")
add_executable( ${PROJECT_NAME} ${SOURCES})

cmake_minimum_required(VERSION 2.8...3.13)

project(hello-world C CXX)

# add build example VideoCapture and VideoDisplay
# more example in: vision-rv1126-buildroot/external/rkmedia/examples
add_subdirectory(rkmedia_example)

set(CMAKE_C_STANDARD 99)

add_executable(${PROJECT_NAME} main.c)


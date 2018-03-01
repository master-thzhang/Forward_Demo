cmake_minimum_required(VERSION 2.8)
project(Forward)

set(CMAKE_CXX_STANDARD 11)


find_package( OpenCV REQUIRED )
message("Open CV version is ${OpenCV_VERSION}")
# Uncomment for no display (e.g. AWS instance)
set(Opencv_DEFINITIONS -DNO_DISPLAY)
# add_definitions(${Opencv_DEFINITIONS})
message("Opencv_DEFINITIONS is ${Opencv_DEFINITIONS}")
include_directories(${OPENCV_INCLUDE_DIRS})

add_executable(Forward main.cpp src/Network.cpp src/Network.h src/quantize.h src/image_proc.h include/DAC_include.h include/NETNAME.h src/string_op.h)
target_link_libraries(Forward ${OpenCV_LIBS})

CMAKE_MINIMUM_REQUIRED(VERSION 3.0 FATAL_ERROR)

PROJECT(RPIEXAMPLES)

SET(CMAKE_CXX_STANDARD 11)

FIND_PACKAGE(TensorFlowCpp REQUIRED PATHS /usr/lib/cmake/tensorflow-cpp)

INCLUDE_DIRECTORIES(${TENSORFLOWCPP_INCLUDE_DIRS})

ADD_EXECUTABLE(camera camera.cc)
TARGET_LINK_LIBRARIES(camera ${TENSORFLOWCPP_LIBRARIES} -lv4l2 -ljpeg -lz)

ADD_EXECUTABLE(label_image label_image.cc)
TARGET_LINK_LIBRARIES(label_image ${TENSORFLOWCPP_LIBRARIES} -lv4l2 -ljpeg -lz)

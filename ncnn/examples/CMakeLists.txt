
find_package(OpenCV QUIET COMPONENTS core highgui imgproc imgcodecs)
if(NOT OpenCV_FOUND)
    find_package(OpenCV REQUIRED COMPONENTS core highgui imgproc)
endif()

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../src)
include_directories(${CMAKE_CURRENT_BINARY_DIR}/../src)

add_executable(squeezenet squeezenet.cpp)
target_link_libraries(squeezenet ncnn ${OpenCV_LIBS})

add_executable(fasterrcnn fasterrcnn.cpp)
target_link_libraries(fasterrcnn ncnn ${OpenCV_LIBS})

add_executable(yolov2 yolov2.cpp)
target_link_libraries(yolov2 ncnn ${OpenCV_LIBS})

add_executable(xiong_yolo1 xiong_yolo1.cpp)
target_link_libraries(xiong_yolo1 ncnn ${OpenCV_LIBS})

add_subdirectory(ssd)

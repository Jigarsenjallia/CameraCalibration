PROJECT(CameraCalibration)

cmake_minimum_required(VERSION 2.8)
find_package(OpenCV REQUIRED
    opencv_core
    opencv_calib3d
    opencv_imgproc
    opencv_highgui)

find_package(Boost REQUIRED system filesystem regex)

SET(appName cameraCalibration)
SET(calibSrc calibrate.cpp)

ADD_EXECUTABLE(${appName} ${calibSrc})
TARGET_LINK_LIBRARIES( ${appName} ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES( ${appName} ${OpenCV_LIBS} )
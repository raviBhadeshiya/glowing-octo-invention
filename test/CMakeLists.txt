set(GTEST_SHUFFLE 1)

add_executable(
    cpp-test
    main.cpp
    MockCamera.cpp
    MockDetection.cpp
    MockRobot.cpp
    ../app/Camera.cpp
    ../app/Detection.cpp
    ../app/Robot.cpp
)

target_include_directories(cpp-test PUBLIC ../vendor/googletest/googletest/include PUBLIC ../vendor/googletest/googlemock/include ${CMAKE_SOURCE_DIR}/include ${OpenCV_INCLUDE_DIRS})

target_link_libraries(cpp-test PUBLIC gtest PUBLIC gmock ${OpenCV_LIBS})

CMAKE_MINIMUM_REQUIRED(VERSION 3.1)
PROJECT(GTestTest LANGUAGES CXX)

SET(CMAKE_INCLUDE_CURRENT_DIR ON)
SET(CMAKE_AUTOMOC ON)

set (CMAKE_CXX_STANDARD 14)
add_definitions(-DGTEST_LANGUAGE_CXX11)

SET(GTestSrc /usr/src/gtest)
SET(GMockSrc /usr/src/gmock)

include_directories(${GTestSrc} ${GTestSrc}/include ${GMockSrc} ${GMockSrc}/include)
add_executable(${PROJECT_NAME} main.cpp Summator.cpp ${GTestSrc}/src/gtest-all.cc ${GMockSrc}/src/gmock-all.cc )
target_link_libraries(${PROJECT_NAME} ${GTEST_LIBRARIES} pthread)
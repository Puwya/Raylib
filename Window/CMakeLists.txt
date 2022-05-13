cmake_minimum_required(VERSION 3.15) # FetchContent is available in 3.11+
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
project(main)


add_executable(${PROJECT_NAME} src/main.cpp)
#set(raylib_VERBOSE 1)
target_link_directories(main PUBLIC "src/lib/")
target_link_libraries(${PROJECT_NAME} raylib)

# Checks if OSX and links appropriate frameworks (Only required on MacOS)
if (APPLE)
    target_link_libraries(${PROJECT_NAME} "-framework IOKit")
    target_link_libraries(${PROJECT_NAME} "-framework Cocoa")
    target_link_libraries(${PROJECT_NAME} "-framework OpenGL")
endif()
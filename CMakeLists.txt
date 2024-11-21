# Generated from cube.pro.

cmake_minimum_required(VERSION 3.16)
set(_PROJECT_NAME PieMenuTest)
project(${_PROJECT_NAME} LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt6 REQUIRED COMPONENTS Core Gui Widgets)

qt_standard_project_setup(REQUIRES 6.8.0)

qt_add_executable(${_PROJECT_NAME}
    main.cpp
    MainWindow.cpp
    PieMenu.cpp
    resources.qrc
    MainWindow.ui
)

if(ANDROID)
    set_target_properties(${_PROJECT_NAME}
                            PROPERTIES
                           # QT_ANDROID_PACKAGE_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/android
                            QT_ANDROID_TARGET_SDK_VERSION "33")
endif()

set_target_properties(${_PROJECT_NAME} PROPERTIES
    WIN32_EXECUTABLE TRUE
    MACOSX_BUNDLE TRUE
)

target_link_libraries(${_PROJECT_NAME} PUBLIC
    Qt6::Widgets
)

cmake_minimum_required(VERSION 3.16)
project(breeze VERSION 6.8.80 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(QT_MAJOR_VERSION 6)
set(KF6_MIN_VERSION "6.0.0")
set(QT_MIN_VERSION "6.5.0")

find_package(ECM ${KF6_MIN_VERSION} REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH})

include(KDEInstallDirs6)
include(KDECMakeSettings)
include(ECMQtDeclareLoggingCategory)

find_package(Qt6 ${QT_MIN_VERSION} REQUIRED CONFIG COMPONENTS Core Gui Widgets Svg)
find_package(KF6 ${KF6_MIN_VERSION} REQUIRED COMPONENTS
    CoreAddons
    ColorScheme
    Config
    GuiAddons
    I18n
    IconThemes
    WindowSystem
    KCMUtils
)
find_package(KDecoration3 REQUIRED)

add_subdirectory(libbreezecommon libbreezecommon6)
add_subdirectory(kdecoration)

feature_summary(WHAT ALL FATAL_ON_MISSING_REQUIRED_PACKAGES)
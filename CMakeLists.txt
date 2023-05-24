cmake_minimum_required(VERSION 3.14)

project(qt_android_deployment_test LANGUAGES CXX)

find_package(Qt6 REQUIRED COMPONENTS Core Gui)

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(subproject)

qt_add_executable(main1 main1.cpp)
target_link_libraries(main1 PUBLIC sublib Qt::Core Qt::Gui)


install(TARGETS main1
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

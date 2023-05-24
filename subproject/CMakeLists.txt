cmake_minimum_required(VERSION 3.21)

project(sublib_project)

set(CMAKE_CXX_STANDARD 20)


find_package(Qt6 REQUIRED COMPONENTS Core Gui)


add_library(sublib STATIC sublib.cpp)

target_link_libraries(sublib PUBLIC)

qt_add_executable(submain submain.cpp)
target_link_libraries(submain PUBLIC sublib Qt::Core Qt::Gui)
install(TARGETS submain
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

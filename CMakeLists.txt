cmake_minimum_required(VERSION 3.0)

set(PROJECT_NAME "hello")

project(${PROJECT_NAME} VERSION 1.0.0 LANGUAGES CXX)

get_filename_component(ROOT_DIR "${CMAKE_CURRENT_SOURCE_DIR}/.." ABSOLUTE)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -Wall")

add_executable(${PROJECT_NAME}
    ${CMAKE_CURRENT_SOURCE_DIR}/src/test.cpp
)

target_link_libraries(${PROJECT_NAME}
    logging
)


include(GNUInstallDirs)

install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})


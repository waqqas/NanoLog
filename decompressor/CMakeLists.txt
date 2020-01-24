project(decompressor)

file(GLOB SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/*.cc ${NanoLog_SOURCE_DIR}/runtime/testHelper/GeneratedCode.cc)
add_executable(${PROJECT_NAME} ${SOURCES})

target_include_directories(${PROJECT_NAME} PRIVATE ${NanoLog_SOURCE_DIR}/runtime)
target_link_libraries(${PROJECT_NAME} NanoLog)

include(GNUInstallDirs)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME} DESTINATION ${CMAKE_INSTALL_BINDIR})

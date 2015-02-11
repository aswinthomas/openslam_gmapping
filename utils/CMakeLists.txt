include_directories(./)
add_library(utils movement.cpp stat.cpp)
install(TARGETS utils DESTINATION ${CMAKE_INSTALL_LIBDIR})

add_executable(example main.cpp)
target_link_libraries(example PRIVATE ${CMAKE_SOURCE_DIR}/libshared.so)

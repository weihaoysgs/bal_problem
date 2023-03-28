add_executable(test_backend test_backend.cpp)
target_link_libraries(test_backend bal_common ${CERES_LIBS} backend_lib fmt) 
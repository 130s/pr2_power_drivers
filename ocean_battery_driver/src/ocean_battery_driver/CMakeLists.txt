find_library(LOG4CXX_LIBRARY log4cxx)
rosbuild_add_executable(ocean_server server.cpp ocean.cpp)
rosbuild_add_executable(battery_check battery_check.cpp ocean.cpp)

rosbuild_add_boost_directories()
rosbuild_link_boost(ocean_server thread program_options)
rosbuild_link_boost(battery_check thread program_options date_time)
target_link_libraries(ocean_server ${LOG4CXX_LIBRARY})

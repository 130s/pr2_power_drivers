find_library(LOG4CXX_LIBRARY log4cxx)

rosbuild_add_executable(power_node power_node.cpp)
rosbuild_add_executable(power_node2 power_node2.cpp)

rosbuild_add_boost_directories()
rosbuild_link_boost(power_node thread program_options)
rosbuild_link_boost(power_node2 thread program_options)
target_link_libraries(power_node ${LOG4CXX_LIBRARY})
target_link_libraries(power_node2 ${LOG4CXX_LIBRARY})

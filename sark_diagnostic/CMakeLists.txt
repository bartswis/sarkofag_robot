cmake_minimum_required(VERSION 2.8.3)

project(sark_diagnostic)

find_package(catkin REQUIRED COMPONENTS rtt_ros cmake_modules)

find_package(OROCOS-RTT REQUIRED)
find_package(Eigen REQUIRED)
find_package(orocos_kdl REQUIRED)

include_directories(${catkin_INCLUDE_DIRS}  ${Eigen_INCLUDE_DIRS})

orocos_component(sark_diagnostic src/SarkDiagnostic.cpp)
target_link_libraries(sark_diagnostic ${catkin_LIBRARIES} ${orocos_kdl_LIBRARIES})
add_dependencies(sark_diagnostic ${catkin_EXPORTED_TARGETS})


orocos_generate_package()

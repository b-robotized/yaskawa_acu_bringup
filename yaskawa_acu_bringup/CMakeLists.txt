cmake_minimum_required(VERSION 3.8)
project(yaskawa_acu_bringup)

find_package(ament_cmake REQUIRED)

install(
  DIRECTORY config moveit_config launch urdf srdf
  DESTINATION share/${PROJECT_NAME}
)

ament_package()

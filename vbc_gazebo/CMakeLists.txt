cmake_minimum_required(VERSION 3.8)
project(vbc_gazebo)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)

install (
  DIRECTORY models world urdf config rviz 
  DESTINATION share/${PROJECT_NAME}
)

ament_environment_hooks("hooks/vbc_gazebo.dsv.in")
ament_environment_hooks("hooks/vbc_gazebo.sh.in")

ament_package()

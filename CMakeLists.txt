cmake_minimum_required(VERSION 3.8)
project(wujihand-urdf)

find_package(ament_cmake REQUIRED)

install(
    DIRECTORY Description .scripts/launch .scripts/rviz
    DESTINATION share/${PROJECT_NAME}
)

ament_package()

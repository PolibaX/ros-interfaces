cmake_minimum_required(VERSION 3.5)
project(polibax_interfaces)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

find_package(rosidl_default_generators REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/EntityList.msg"
  "msg/DetectedObject.msg"
  "msg/ObjectRegistry.msg"
  "msg/Vec2.msg"
  "msg/Pid.msg"
  "msg/MotorControlStatus.msg"
  "msg/RoverStatus.msg"
  "msg/MissionTask.msg"
  "msg/MissionTaskList.msg"
  "msg/AgentStatus.msg"
  "msg/Entity.msg"
  "srv/StringTrigger.srv"
  "action/Dummy.action"
  "action/Explore.action"
  "action/Land.action"
  "action/MoveTo.action"
  "action/Takeoff.action"
  "action/MissionOrder.action"
  "action/FindTarget.action"
  "srv/Takeoff.srv"
  "srv/Land.srv"
  "srv/Cry.srv"
  "srv/MoveTo.srv"
  "srv/DoublePid.srv"
  "srv/GetMissionTask.srv"
  "srv/GetAllMissionTask.srv"
  "srv/AddMissionTask.srv"
  "srv/SetMissionComplete.srv"
  "srv/GetContext.srv"
  "srv/AskArucoPosition.srv"
  "srv/GetCookie.srv"
  DEPENDENCIES geometry_msgs
  DEPENDENCIES std_msgs
  DEPENDENCIES sensor_msgs
 )


if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
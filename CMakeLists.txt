cmake_minimum_required(VERSION 3.5)
project(v2x_cohdainterfaces)

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
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/GPS.msg"
  "msg/MAPEM.msg"
  "msg/SPATEM.msg"
  "msg/spat/SPAT.msg"
  "msg/spat/Intersection.msg"
  "msg/spat/IntersectionID.msg"
  "msg/spat/SignalState.msg"
  "msg/spat/StateTimeSpeed.msg"
  "msg/spat/Timing.msg"
  "msg/spat/Speed.msg"
  "msg/spat/ManeuverAssist.msg"
  "msg/spat/Regional.msg"
  "msg/mapem/MapemMapData.msg"
  "msg/mapem/MapemIntersection.msg"
  "msg/mapem/MapemIntersectionID.msg"
  "msg/mapem/MapemReferencePoint.msg"
  "msg/mapem/MapemSpeedLimit.msg"
  "msg/mapem/MapemLane.msg"
  "msg/mapem/MapemLaneAttributes.msg"
  "msg/mapem/MapemNodeList.msg"
  "msg/mapem/MapemConnection.msg"
  "msg/mapem/MapemConnectingLane.msg"
  "msg/mapem/MapemRemoteIntersection.msg"
  "msg/mapem/MapemPreemptPriorityData.msg"
  "msg/mapem/MapemZone.msg"
  "msg/mapem/MapemRoadSegment.msg"
  "msg/mapem/MapemDataParameters.msg"
  "msg/mapem/MapemRestriction.msg"
  "msg/mapem/MapemUserRestriction.msg"
  "msg/mapem/MapemRegional.msg"
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

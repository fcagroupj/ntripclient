cmake_minimum_required(VERSION 3.0.2)
project(ntripclient)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(Boost REQUIRED)
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  nodelet
  pluginlib
  message_filters
  ce_sen_msgs
)

# BNC
find_package(Qt5 COMPONENTS Core Network Gui Widgets REQUIRED)
set(CMAKE_AUTOMOC ON)
# find_package(Newmat REQUIRED)

## System dependencies are found with CMake's conventions
# find_package(Boost REQUIRED COMPONENTS system)

# Define preprocessor macro
add_compile_definitions(_TTY_POSIX_)

## Uncomment this if the package has a setup.py. This macro ensures
## modules and global scripts declared therein get installed
## See http://ros.org/doc/api/catkin/html/user_guide/setup_dot_py.html
# catkin_python_setup()

################################################
## Declare ROS messages, services and actions ##
################################################

## To declare and build messages, services or actions from within this
## package, follow these steps:
## * Let MSG_DEP_SET be the set of packages whose message types you use in
##   your messages/services/actions (e.g. std_msgs, actionlib_msgs, ...).
## * In the file package.xml:
##   * add a build_depend tag for "message_generation"
##   * add a build_depend and a exec_depend tag for each package in MSG_DEP_SET
##   * If MSG_DEP_SET isn't empty the following dependency has been pulled in
##     but can be declared for certainty nonetheless:
##     * add a exec_depend tag for "message_runtime"
## * In this file (CMakeLists.txt):
##   * add "message_generation" and every package in MSG_DEP_SET to
##     find_package(catkin REQUIRED COMPONENTS ...)
##   * add "message_runtime" and every package in MSG_DEP_SET to
##     catkin_package(CATKIN_DEPENDS ...)
##   * uncomment the add_*_files sections below as needed
##     and list every .msg/.srv/.action file to be processed
##   * uncomment the generate_messages entry below
##   * add every package in MSG_DEP_SET to generate_messages(DEPENDENCIES ...)

## Generate messages in the 'msg' folder
# add_message_files(
#   FILES
#   Message1.msg
#   Message2.msg
# )

## Generate services in the 'srv' folder
# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

## Generate added messages and services with any dependencies listed here
# generate_messages(
#   DEPENDENCIES
#   std_msgs
# )

################################################
## Declare ROS dynamic reconfigure parameters ##
################################################

## To declare and build dynamic reconfigure parameters within this
## package, follow these steps:
## * In the file package.xml:
##   * add a build_depend and a exec_depend tag for "dynamic_reconfigure"
## * In this file (CMakeLists.txt):
##   * add "dynamic_reconfigure" to
##     find_package(catkin REQUIRED COMPONENTS ...)
##   * uncomment the "generate_dynamic_reconfigure_options" section below
##     and list every .cfg file to be processed

## Generate dynamic reconfigure parameters in the 'cfg' folder
# generate_dynamic_reconfigure_options(
#   cfg/DynReconf1.cfg
#   cfg/DynReconf2.cfg
# )

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if your package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
  INCLUDE_DIRS include
  LIBRARIES ntripclient_nodelet 
  CATKIN_DEPENDS roscpp message_runtime std_msgs nodelet pluginlib message_filters
  EXPORTED_TARGETS
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
  ${catkin_INCLUDE_DIRS}
  include
  src
  src/RTCM3
  src/rinex
  src/combination
  src/upload
  src/RTCM
  src/RTCM3/clock_and_orbit
  src/serial
  newmat
)

## link_directories(
##   /usr/lib/x86_64-linux-gnu
## )
###########################################################
##################### ntripclient_nodelet ####################
###########################################################
add_library(ntripclient_nodelet
  src/ntripclient_nodelet.cpp
  src/bncantex.cpp
  src/bnccaster.cpp
  src/bncclockrinex.cpp
  src/bncconst.cpp
  src/bnccore.cpp
  src/bncephuser.cpp
  src/bncgetthread.cpp
  src/bncmain.cpp
  src/bncnetqueryv1.cpp
  src/bncoutf.cpp
  src/bncrawfile.cpp
  src/bncrinex.cpp
  src/bncsettings.cpp
  src/bncsp3.cpp
  src/bnctableitem.cpp
  src/bnctime.cpp
  src/bncutils.cpp
  src/ephemeris.cpp
  src/GPSDecoder.cpp
  src/latencychecker.cpp
  src/pppModel.cpp
  src/satObs.cpp
  src/t_prn.cpp
  src/combination/bnccomb.cpp
  src/rinex/rnxnavfile.cpp
  src/rinex/rnxobsfile.cpp
  src/RTCM3/RTCM3coDecoder.cpp
  src/RTCM3/RTCM3Decoder.cpp
  src/RTCM3/clock_and_orbit/clock_orbit_igs.cpp
  src/RTCM3/clock_and_orbit/clock_orbit_rtcm.cpp
  src/RTCM/rtcm_utils.cpp
  src/serial/posix_qextserialport.cpp
  src/serial/qextserialbase.cpp
  src/serial/qextserialport.cpp
  src/upload/bncrtnetdecoder.cpp
  src/upload/bncrtnetuploadcaster.cpp
  src/upload/bncuploadcaster.cpp
  newmat/bandmat.cpp
  newmat/cholesky.cpp
  newmat/evalue.cpp
  newmat/fft.cpp
  newmat/hholder.cpp
  newmat/jacobi.cpp
  newmat/myexcept.cpp
  newmat/newfft.cpp
  newmat/newmat1.cpp
  newmat/newmat2.cpp
  newmat/newmat3.cpp
  newmat/newmat4.cpp
  newmat/newmat5.cpp
  newmat/newmat6.cpp
  newmat/newmat7.cpp
  newmat/newmat8.cpp
  newmat/newmat9.cpp
  newmat/newmatex.cpp
  newmat/newmatrm.cpp
  newmat/nm_misc.cpp
  newmat/sort.cpp
  newmat/submat.cpp
  newmat/svd.cpp
)

target_link_libraries(ntripclient_nodelet
   Qt5::Core	
   Qt5::Network
   Qt5::Gui
   Qt5::Widgets
   ${catkin_LIBRARIES}
)

target_include_directories(ntripclient_nodelet 
  SYSTEM PUBLIC
) 

add_dependencies(ntripclient_nodelet 
  ${${PROJECT_NAME}_EXPORTED_TARGETS} 
  ${catkin_EXPORTED_TARGETS}
)

add_executable(ntripclient_node
  src/ntripclient_node.cpp
)

add_dependencies(ntripclient_node 
  ${${PROJECT_NAME}_EXPORTED_TARGETS} 
  ${catkin_EXPORTED_TARGETS}
)

target_link_libraries(ntripclient_node
   ${catkin_LIBRARIES}
)

#############
## Install ##
#############

# all install targets should use catkin DESTINATION variables
# See http://ros.org/doc/api/catkin/html/adv_user_guide/variables.html

## Mark executable scripts (Python etc.) for installation
## in contrast to setup.py, you can choose the destination
# catkin_install_python(PROGRAMS
#   scripts/my_python_script
#   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
# )

## Mark executables for installation
## See http://docs.ros.org/melodic/api/catkin/html/howto/format1/building_executables.html
# install(TARGETS ${PROJECT_NAME}_node
#   RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
# )

## Mark libraries for installation
## See http://docs.ros.org/melodic/api/catkin/html/howto/format1/building_libraries.html
# install(TARGETS ${PROJECT_NAME}
#   ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
#   LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
#   RUNTIME DESTINATION ${CATKIN_GLOBAL_BIN_DESTINATION}
# )

## Mark cpp header files for installation
# install(DIRECTORY include/${PROJECT_NAME}/
#   DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
#   FILES_MATCHING PATTERN "*.h"
#   PATTERN ".svn" EXCLUDE
# )

## Mark other files for installation (e.g. launch and bag files, etc.)
# install(FILES
#   # myfile1
#   # myfile2
#   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
# )

#############
## Testing ##
#############

## Add gtest based cpp test target and link libraries
# catkin_add_gtest(${PROJECT_NAME}-test test/test_ntripclient.cpp)
# if(TARGET ${PROJECT_NAME}-test)
#   target_link_libraries(${PROJECT_NAME}-test ${PROJECT_NAME})
# endif()

## Add folders to be run by python nosetests
# catkin_add_nosetests(test)

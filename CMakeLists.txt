cmake_minimum_required(VERSION 2.8.3)
project(hear_msgs)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
)

add_message_files(
  FILES
  MRFT_param.msg
  PID_param.msg
)

add_service_files(
   FILES
   get_float.srv
   set_bool.srv
   set_float.srv
   Update_Controller_MRFT.srv
   Update_Controller_PID.srv
) 

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime
    roscpp
    std_msgs
)

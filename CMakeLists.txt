### Maintainer: flier[@techfak.uni-bielefeld.de] ###

CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3)

PROJECT(clf_perception_vision_msgs)

FIND_PACKAGE(catkin REQUIRED COMPONENTS roscpp
                                        std_msgs
                                        message_generation
                                        message_filters
                                        sensor_msgs
                                        message_runtime
                                        geometry_msgs
                                        people_msgs
                                        visualization_msgs
)

ADD_MESSAGE_FILES(
   DIRECTORY msg
   FILES
   ExtendedPersonStamped.msg
   ExtendedObjectsStamped.msg
   ExtendedPoseArray.msg
   ExtendedPeople.msg
   ExtendedObjects.msg
)

ADD_SERVICE_FILES(
   DIRECTORY srv
   FILES
   DoIKnowThatPerson.srv
   LearnPerson.srv
   MoodOfPerson.srv
)

GENERATE_MESSAGES(DEPENDENCIES geometry_msgs std_msgs sensor_msgs people_msgs visualization_msgs)

CATKIN_PACKAGE(CATKIN_DEPENDS roscpp
                              std_msgs
                              message_generation
                              message_filters
                              sensor_msgs
                              message_runtime
                              geometry_msgs
                              people_msgs
                              visualization_msgs
)


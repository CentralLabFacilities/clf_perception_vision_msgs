### Maintainer: flier[@techfak.uni-bielefeld.de] ###

CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3)

PROJECT(clf_perception_vision_msgs)

FIND_PACKAGE(catkin REQUIRED COMPONENTS tf
                                        roscpp
                                        nodelet
                                        std_msgs
                                        cv_bridge
                                        sensor_msgs
                                        geometry_msgs
                                        message_filters
                                        image_transport
                                        visualization_msgs
                                        message_generation
)

ADD_MESSAGE_FILES(
   DIRECTORY msg
   FILES
   ExtendedPersonStamped.msg
   ExtendedObjectsStamped.msg
   ExtendedPeople.msg
   ExtendedObjects.msg
)

ADD_SERVICE_FILES(
   DIRECTORY srv
   FILES
   DoIKnowThatPerson.srv
   LearnPerson.srv
)

GENERATE_MESSAGES(DEPENDENCIES geometry_msgs std_msgs)

CATKIN_PACKAGE(INCLUDE_DIRS include
               # LIBRARIES clf_perception_nodelets
               CATKIN_DEPENDS tf
                              roscpp
                              nodelet
                              std_msgs
                              cv_bridge
                              sensor_msgs
                              geometry_msgs
                              message_filters
                              message_runtime
                              image_transport
)


CATKIN_INSTALL_PYTHON(PROGRAMS src/python/clf_perception_box2people.py DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
CATKIN_INSTALL_PYTHON(PROGRAMS src/python/clf_perception_box2objects.py DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

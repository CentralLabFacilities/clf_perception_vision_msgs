### Maintainer: flier[@techfak.uni-bielefeld.de] ###

CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3)

PROJECT(clf_perception_vision_msgs)

FIND_PACKAGE(catkin REQUIRED COMPONENTS
                                        std_msgs
                                        message_generation
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
   CMTrackerResults.msg
)

ADD_SERVICE_FILES(
   DIRECTORY srv
   FILES
   DoIKnowThatPerson.srv
   LearnPerson.srv
   MoodOfPerson.srv
   LearnPersonImage.srv
   DoIKnowThatPersonImage.srv
   CMTObjectTrack.srv
   CMTStopObjectTrack.srv
   ClassifyGenderAgeImage.srv
   ToggleCFtldTrackingWithBB.srv
)

GENERATE_MESSAGES(DEPENDENCIES geometry_msgs std_msgs sensor_msgs people_msgs visualization_msgs)

CATKIN_PACKAGE(CATKIN_DEPENDS roscpp
                              std_msgs
                              message_generation
                              
                              sensor_msgs
                              geometry_msgs
                              people_msgs
                              visualization_msgs
)


cmake_minimum_required(VERSION 2.8)


SET(TRWS_SRC_FILES
  minimize.cpp
  MRFEnergy.cpp
  ordering.cpp
  treeProbabilities.cpp
)


#include_directories( ad3 )
#include_directories( Eigen )


ADD_LIBRARY(opengm-external-trws   ${TRWS_SRC_FILES})
ADD_LIBRARY(opengm-external-trws-shared   SHARED ${TRWS_SRC_FILES} )

install (TARGETS opengm-external-trws DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-trws-shared DESTINATION lib/opengm/externals/)


install(DIRECTORY "."
    DESTINATION include/opengm/externals/trws
    FILES_MATCHING
    PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)
#
#install(DIRECTORY Eigen
#    DESTINATION include/opengm/externals
#    PATTERN ".svn" EXCLUDE
#)


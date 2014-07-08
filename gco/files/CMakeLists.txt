cmake_minimum_required(VERSION 2.8)

SET(GCO_SRC_FILES
  GCoptimization.cpp
  graph.cpp
  LinkedBlockList.cpp
  maxflow.cpp
  instances.inc
)



ADD_LIBRARY(opengm-external-gco   ${GCO_SRC_FILES})
ADD_LIBRARY(opengm-external-gco-shared   SHARED ${GCO_SRC_FILES} )

install (TARGETS opengm-external-gco DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-gco-shared DESTINATION lib/opengm/externals/)


install(DIRECTORY .
    DESTINATION include/opengm/externals/gco
    FILES_MATCHING
    PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)



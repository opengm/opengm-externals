cmake_minimum_required(VERSION 2.8)


 SET(MAXFLOW_SRC_FILES
        graph.cpp
        maxflow.cpp
)

ADD_LIBRARY(opengm-external-maxflow ${MAXFLOW_SRC_FILES})
ADD_LIBRARY(opengm-external-maxflow-shared SHARED ${MAXFLOW_SRC_FILES})

install (TARGETS opengm-external-maxflow DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-maxflow-shared DESTINATION lib/opengm/externals/)

install(DIRECTORY "."
    DESTINATION include/opengm/externals/maxflow
    FILES_MATCHING
    PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)

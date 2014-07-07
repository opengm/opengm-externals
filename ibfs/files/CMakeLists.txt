cmake_minimum_required(VERSION 2.8)



SET(MAXFLOW_IBFS_SRC_FILES
    ibfs.cpp
)

#include_directories( ad3 )
#include_directories( Eigen )


ADD_LIBRARY(opengm-external-maxflow-ibfs   ${MAXFLOW_IBFS_SRC_FILES})
ADD_LIBRARY(opengm-external-maxflow-ibfs-shared   SHARED ${MAXFLOW_IBFS_SRC_FILES} )

install (TARGETS opengm-external-maxflow-ibfs DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-maxflow-ibfs-shared DESTINATION lib/opengm/externals/)


install(DIRECTORY ibfs
    DESTINATION include/opengm/externals/ibfs
    FILES_MATCHING
    PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)

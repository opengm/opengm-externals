cmake_minimum_required(VERSION 2.8)

SET(QPBO_SRC_FILES
  QPBO_extra.cpp
  QPBO.cpp
  QPBO_maxflow.cpp
  QPBO_postprocessing.cpp
)

ADD_LIBRARY(opengm-external-qpbo ${QPBO_SRC_FILES})
ADD_LIBRARY(opengm-external-qpbo-shared SHARED ${QPBO_SRC_FILES})

install (TARGETS opengm-external-qpbo DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-qpbo-shared DESTINATION lib/opengm/externals/)

install (FILES QPBO.h DESTINATION include/opengm/externals/qpbo)
install (FILES block.h DESTINATION include/opengm/externals/qpbo)
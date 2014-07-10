cmake_minimum_required(VERSION 2.8)


SET(FASTPD_SRC_FILES
    ${FASTPD_PATCHEDSRCDIR}/graph.cpp
    ${FASTPD_PATCHEDSRCDIR}/LinkedBlockList.cpp
    ${FASTPD_PATCHEDSRCDIR}/maxflow.cpp
)


ADD_LIBRARY(opengm-external-fastpd   ${FASTPD_SRC_FILES})
ADD_LIBRARY(opengm-external-fastpd-shared   SHARED ${FASTPD_SRC_FILES} )

install (TARGETS opengm-external-fastpd DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-fastpd-shared DESTINATION lib/opengm/externals/)


install(DIRECTORY "."
    DESTINATION include/opengm/externals/fastpd
    FILES_MATCHING
    PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)

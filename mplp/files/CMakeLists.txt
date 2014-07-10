cmake_minimum_required(VERSION 2.8)


SET(MPLP_SRC_FILES
    matrix.cpp
    mplp_alg.cpp
    muldim_arr.cpp
    read_model_file.cpp
)

#include_directories( ad3 )
#include_directories( Eigen )

ADD_LIBRARY(opengm-external-mplp   ${MPLP_SRC_FILES})
ADD_LIBRARY(opengm-external-mplp-shared   SHARED ${MPLP_SRC_FILES} )

install (TARGETS opengm-external-mplp DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-mplp-shared DESTINATION lib/opengm/externals/)


install(DIRECTORY "."
    DESTINATION include/opengm/externals/mplp
    FILES_MATCHING
    PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
)

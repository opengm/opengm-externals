cmake_minimum_required(VERSION 2.8)

SET(CONICBUNDLE_SRC_FILES
${CURRENT_SOURCE_DIR}CBsources/lmaxproblem.cxx
${CURRENT_SOURCE_DIR}CBsources/funproblem.cxx
${CURRENT_SOURCE_DIR}CBsources/MatSDPfun.cxx
${CURRENT_SOURCE_DIR}CBsources/coneproblem.cxx
${CURRENT_SOURCE_DIR}CBsources/sumproblem.cxx
${CURRENT_SOURCE_DIR}CBsources/MatFCBSolver.cxx
${CURRENT_SOURCE_DIR}CBsources/Nbundle.cxx
${CURRENT_SOURCE_DIR}CBsources/socproblem.cxx
${CURRENT_SOURCE_DIR}CBsources/MatNBSolver.cxx
${CURRENT_SOURCE_DIR}CBsources/qp_sdpblock.cxx
${CURRENT_SOURCE_DIR}CBsources/bundle.cxx
${CURRENT_SOURCE_DIR}CBsources/qp_solver.cxx
${CURRENT_SOURCE_DIR}CBsources/lowranktrSMscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/lowrankSMscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/MatCBSolver.cxx
${CURRENT_SOURCE_DIR}CBsources/lowranktrscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/lowrankscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/CB_CSolver.cxx
${CURRENT_SOURCE_DIR}CBsources/CBSolver.cxx
${CURRENT_SOURCE_DIR}CBsources/Nfunproblem.cxx
${CURRENT_SOURCE_DIR}CBsources/diagtrscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/MatConcavefun.cxx
${CURRENT_SOURCE_DIR}CBsources/diagscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/fulltrscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/bigmat.cxx
${CURRENT_SOURCE_DIR}CBsources/fullscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/MatLPBCfun.cxx
${CURRENT_SOURCE_DIR}CBsources/idscaling.cxx
${CURRENT_SOURCE_DIR}CBsources/MatConefun.cxx
${CURRENT_SOURCE_DIR}CBsources/Nsumproblem.cxx
${CURRENT_SOURCE_DIR}CBsources/problem.cxx
${CURRENT_SOURCE_DIR}CBsources/hkweight.cxx
${CURRENT_SOURCE_DIR}CBsources/MatLPfun.cxx
${CURRENT_SOURCE_DIR}CBsources/coeffmat.cxx
${CURRENT_SOURCE_DIR}CBsources/CFunction.cxx
${CURRENT_SOURCE_DIR}CBsources/MatSOCfun.cxx    
${CURRENT_SOURCE_DIR}Matrix/sparsmat.cxx
${CURRENT_SOURCE_DIR}Matrix/lanczpol.cxx
${CURRENT_SOURCE_DIR}Matrix/sparssym.cxx
${CURRENT_SOURCE_DIR}Matrix/matrix.cxx
${CURRENT_SOURCE_DIR}Matrix/symmat.cxx
${CURRENT_SOURCE_DIR}Matrix/indexmat.cxx
${CURRENT_SOURCE_DIR}Matrix/eigval.cxx
${CURRENT_SOURCE_DIR}Matrix/qr.cxx
${CURRENT_SOURCE_DIR}Matrix/memarray.cxx
${CURRENT_SOURCE_DIR}Matrix/chol.cxx
${CURRENT_SOURCE_DIR}Matrix/nnls.cxx
${CURRENT_SOURCE_DIR}Matrix/ldl.cxx
${CURRENT_SOURCE_DIR}Matrix/trisolve.cxx
)


include_directories( include )
include_directories( Matrix )
include_directories( Tools )
include_directories( CBsources )

ADD_LIBRARY(opengm-external-conicbundle   ${CONICBUNDLE_SRC_FILES})
ADD_LIBRARY(opengm-external-conicbundle-shared   SHARED ${CONICBUNDLE_SRC_FILES} )

install (TARGETS opengm-external-conicbundle DESTINATION lib/opengm/externals/)
install (TARGETS opengm-external-conicbundle-shared DESTINATION lib/opengm/externals/)


#install(DIRECTORY ""
#    DESTINATION include/opengm/externals/conicbundle
#    FILES_MATCHING
#    PATTERN "*.h"
#    PATTERN ".svn" EXCLUDE
#)




install(DIRECTORY ${CURRENT_SOURCE_DIR}CBsources
    DESTINATION include/opengm/externals/conicbundle/cb
    FILES_MATCHING
    PATTERN "*.hxx"
    PATTERN ".svn" EXCLUDE
)

install(DIRECTORY ${CURRENT_SOURCE_DIR}Tools
    DESTINATION include/opengm/externals/conicbundle/Tools
    FILES_MATCHING
    PATTERN "*.hxx"
    PATTERN ".svn" EXCLUDE
)

install(DIRECTORY ${CURRENT_SOURCE_DIR}Matrix
    DESTINATION include/opengm/externals/conicbundle/Tools
    FILES_MATCHING
    PATTERN "*.hxx"
    PATTERN ".svn" EXCLUDE
)

install(DIRECTORY ${CURRENT_SOURCE_DIR}include
    DESTINATION include/opengm/externals/conicbundle
    FILES_MATCHING
    PATTERN "*.hxx"
    PATTERN ".svn" EXCLUDE
)

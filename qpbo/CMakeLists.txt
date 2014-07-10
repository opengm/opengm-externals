
include(ExternalProject)
externalproject_add( qpbo
    URL         http://pub.ist.ac.at/~vnk/software/QPBO-v1.3.src.tar.gz
    PATCH_COMMAND patch 
        -s -d ${PROJECT_BINARY_DIR}/qpbo/qpbo-prefix/src/qpbo -p1 < ${PROJECT_SOURCE_DIR}/qpbo/files/QPBO-v1.3.patch -N -r -
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
)

ExternalProject_Add_Step(qpbo copyCMakeFile
  COMMAND ${CMAKE_COMMAND} -E copy ${PROJECT_SOURCE_DIR}/qpbo/files/CMakeLists.txt ${PROJECT_BINARY_DIR}/qpbo/qpbo-prefix/src/qpbo/CMakeLists.txt
  DEPENDEES patch
  DEPENDERS configure
) 



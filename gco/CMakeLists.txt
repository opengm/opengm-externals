
include(ExternalProject)
externalproject_add( gco
    URL http://vision.csd.uwo.ca/code/gco-v3.0.zip
    PATCH_COMMAND patch 
        -s -d ${PROJECT_BINARY_DIR}/gco/gco-prefix/src/gco -p0 < ${PROJECT_SOURCE_DIR}/gco/files/GCO-v3.0.patch -N -r -
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
)

ExternalProject_Add_Step(gco e2
  COMMAND ${CMAKE_COMMAND} -E copy ${PROJECT_SOURCE_DIR}/gco/files/CMakeLists.txt ${PROJECT_BINARY_DIR}/gco/gco-prefix/src/gco/CMakeLists.txt
  DEPENDEES patch
  DEPENDERS configure
) 



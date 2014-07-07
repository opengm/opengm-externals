
include(ExternalProject)
externalproject_add( trws
    URL http://ftp.research.microsoft.com/downloads/dad6c31e-2c04-471f-b724-ded18bf70fe3/TRW_S-v1.3.zip
    PATCH_COMMAND patch 
        -s -d ${PROJECT_BINARY_DIR}/trws/trws-prefix/src/trws -p1 < ${PROJECT_SOURCE_DIR}/trws/files/TRWS-v1.3.patch -N -r -
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
)

ExternalProject_Add_Step(trws e2
  COMMAND ${CMAKE_COMMAND} -E copy ${PROJECT_SOURCE_DIR}/trws/files/CMakeLists.txt ${PROJECT_BINARY_DIR}/trws/trws-prefix/src/trws/CMakeLists.txt
  DEPENDEES patch
  DEPENDERS configure
) 



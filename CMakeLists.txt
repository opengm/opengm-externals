cmake_minimum_required(VERSION 2.8)
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/modules)



option(WITH_QPBO            "DOWNLOAD AND BUILD QPBO"         ON)
option(WITH_AD3             "DOWNLOAD AND BUILD AD3"          ON)
option(WITH_TRWS            "DOWNLOAD AND BUILD TRWS"         ON)
option(WITH_MRF            "DOWNLOAD AND BUILD TRWS"         ON)
option(WITH_IBFS            "DOWNLOAD AND BUILD IBFS"         ON)
option(WITH_MAXFLOW         "DOWNLOAD AND BUILD MAXFLOW"      ON)
option(WITH_GCO             "DOWNLOAD AND BUILD GCO"          ON)
option(WITH_CONICBUNDLE     "DOWNLOAD AND BUILD CONICBUNDLEO" ON)
option(WITH_DAOOPT          "DOWNLOAD AND BUILD DAOOPT"       ON)
option(WITH_LIBDAI          "DOWNLOAD AND BUILD LIBDAI"       OFF)
option(WITH_MPLP            "DOWNLOAD AND BUILD MPLP"         ON)
option(WITH_FASTPD          "DOWNLOAD AND BUILD FASTPD"       OFF)
option(WITH_GRANTE          "DOWNLOAD AND BUILD GRANTE"       OFF)

if(WITH_QPBO)
    add_subdirectory(qpbo)
endif()

if(WITH_AD3)
    add_subdirectory(ad3)
endif()

if(WITH_TRWS)
    add_subdirectory(trws)
endif()

if(WITH_IBFS)
    add_subdirectory(ibfs) 
endif()

if(WITH_MAXFLOW)
    add_subdirectory(maxflow)
endif()

if(WITH_MRF)
    add_subdirectory(mrf)
endif()

if(WITH_GCO)
    add_subdirectory(gco) 
endif()

if(WITH_CONICBUNDLE)
    add_subdirectory(conicbundle)
endif()

if(WITH_DAOOPT)
    add_subdirectory(daoopt)  
endif()

if(WITH_LIBDAI)
    find_package(GMP REQUIRED) 
    find_package(GMPXX REQUIRED) 
    add_subdirectory(libdai)  
endif()

if(WITH_MPLP)
    add_subdirectory(mplp)  
endif()


if(WITH_FASTPD)
    message(SEND_ERROR "DOWNLOAD AND PATCHING OF FastPD IS NOT WORK YET. DISABLE OPTION: 'WITH_FASTPD' ")
    if(NOT FASTPD_URL)
        message(  SEND_ERROR "FASTPD_URL is empty, needs a valid download url to be stored in CMakeVariable FASTPD_URL\n(Registration required at http://www.csd.uoc.gr/~komod/FastPD/)")
    endif()
    add_subdirectory(fastpd)   # patch is not working
endif()


if(WITH_GRANTE)
    message(SEND_ERROR "DOWNLOAD AND PATCHING OF GRANTE IS NOT YET IMPLEMENTED. DISABLE OPTION: 'WITH_GRANTE' ")
endif()

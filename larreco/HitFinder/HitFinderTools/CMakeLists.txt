cet_enable_asserts()

set( hitfinder_tool_lib_list
                        larreco_RecoAlg
                        larcorealg::Geometry
                        lardataobj::RecoBase
                        larcore::Geometry_Geometry_service
                        lardata::Utilities
                        nurandom::RandomUtils_NuRandomService_service
                        MarqFitAlg
                        art::Framework_Core
                        art::Framework_Principal
                        art::Framework_Services_Registry
                        art::Persistency_Common
                        art::Persistency_Provenance
                        art_root_io::tfile_support ROOT::Core
                        art_root_io::TFileService_service
                        art::Utilities
                        canvas::canvas
                        messagefacility::MF_MessageLogger
                        fhiclcpp::fhiclcpp
                        cetlib::cetlib
                        Boost::filesystem
                        art::Framework_Services_Registry art::Framework_Services_FileServiceInterfaces
                        art_root_io::tfile_support ROOT::Core
                        art::Framework_Services_System_FloatingPointControl_service
                        art_root_io::TFileService_service
                        art::Framework_Services_System_FileCatalogMetadata_service
                        CLHEP::Random
    )

include(FindOpenMP)
if(OPENMP_FOUND)
  # even if OpenMP is found on a SLF6 machine, it cannot be used.
  # see the discussion in https://cdcvs.fnal.gov/redmine/issues/23001
  if( ${CMAKE_HOST_SYSTEM_VERSION} MATCHES "^2.6.32.*" )
    message(STATUS "OpenMP is not supported on SLF6")
  else()
    add_definitions(-DWITH_OPENMP)
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} ${OpenMP_EXE_LINKER_FLAGS}")
  endif()
endif(OPENMP_FOUND)

art_make(TOOL_LIBRARIES ${hitfinder_tool_lib_list} )

install_headers()
install_source()
install_fhicl()

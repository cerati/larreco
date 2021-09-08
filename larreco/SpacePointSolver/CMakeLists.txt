include_directories(${CMAKE_CURRENT_SOURCE_DIR})
add_subdirectory(HitReaders)

art_make(LIB_LIBRARIES
           larcorealg::Geometry
           lardataalg::DetectorInfo
           art::Framework_Services_Registry
           art::Utilities
           ROOT::Core
           ROOT::Physics
         MODULE_LIBRARIES
           larcorealg::Geometry
           lardataobj::RecoBase
           larsim::MCCheater_BackTrackerService_service
           lardata::ArtDataHelper
           larreco::SpacePointSolver
           art::Framework_Services_Registry
           ROOT::Core
           ROOT::Hist
        )

install_headers()
install_fhicl()
install_source()

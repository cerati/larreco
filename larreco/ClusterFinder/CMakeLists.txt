art_make(LIB_LIBRARIES
           lardataobj::RecoBase
         MODULE_LIBRARIES
           larreco::Calorimetry
           larreco::RecoAlg_Cluster3DAlgs
           larreco::RecoAlg_TCAlg
           larreco::RecoAlg
           larreco::ClusterFinder
           larsim::MCCheater_ParticleInventoryService_service
           lardataobj::AnalysisBase
           lardataobj::RecoBase
           nurandom::RandomUtils_NuRandomService_service
           nusimdata::SimulationBase
           art::Framework_Services_Registry
           art_root_io::tfile_support
           ROOT::Core
           ROOT::Physics
           art_root_io::TFileService_service
           messagefacility::MF_MessageLogger
         )

install_headers()
install_fhicl()
install_source()

add_subdirectory(RStarTree)
add_subdirectory(TrackShowerSplitter)

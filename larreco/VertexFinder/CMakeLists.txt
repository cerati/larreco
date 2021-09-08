art_make(EXCLUDE FeatureVertexFinder_module.cc
         MODULE_LIBRARIES
           larsim::MCCheater_ParticleInventoryService_service
           lardataobj::RecoBase
           larcorealg::Geometry
           larreco_RecoAlg
           nusimdata::SimulationBase
           lardata::RecoObjects
           art::Framework_Services_Registry
           art_root_io::TFileService_service
           art_root_io::tfile_support
           ROOT::Core
           ROOT::Hist
           ROOT::Physics
           messagefacility::MF_MessageLogger
         )

simple_plugin(FeatureVertexFinder "module"
                messagefacility::MF_MessageLogger
                art::Framework_Services_Registry
                ROOT::Core
                ROOT::Hist
                larcorealg::Geometry
                lardataalg::DetectorInfo
                lardataobj::RecoBase
              )

install_fhicl()
install_source()

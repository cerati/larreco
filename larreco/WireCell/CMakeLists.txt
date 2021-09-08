art_make(MODULE_LIBRARIES
           larcorealg::Geometry
           lardataobj::RawData
           lardataobj::RecoBase
           nusimdata::SimulationBase
           art::Framework_Services_Registry
           ROOT::Core
           ROOT::RIO
           ROOT::Tree
           messagefacility::MF_MessageLogger
           ROOT::EG
           ROOT::Hist
           ROOT::Physics
        )

# install_headers()
install_fhicl()
install_source()

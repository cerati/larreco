art_make(LIB_LIBRARIES
           lardataalg_DetectorInfo
           lardataobj_RecoBase
           lardata_ArtDataHelper
           larcorealg_Geometry
           lardataobj_AnalysisBase
           art::Framework_Services_Registry
           fhiclcpp::fhiclcpp
           cetlib::cetlib
           cetlib_except::cetlib_except
           art::Utilities
           fhiclcpp::fhiclcpp fhiclcpp::types
           messagefacility::MF_MessageLogger
           ROOT::Core
           ROOT::Physics
         MODULE_LIBRARIES
           larcorealg_Geometry
           larreco_Calorimetry
           ROOT::Core
           ROOT::Hist
           ROOT::Physics
           messagefacility::MF_MessageLogger)

install_headers()
install_fhicl()
install_source()

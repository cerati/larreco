art_make(MODULE_LIBRARIES
  lardataalg::DetectorInfo
  larcorealg::Geometry
  lardataobj::RecoBase
  art::Framework_Services_Registry
  ROOT::Core
  ROOT::Physics
  art_root_io::TFileService_service
  messagefacility::MF_MessageLogger
  )

install_headers()
install_fhicl()
install_source()

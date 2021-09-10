
art_make(LIB_LIBRARIES
           lardataalg::DetectorInfo
           larcorealg::Geometry
           larreco::RecoAlg_TCAlg
           larreco::RecoAlg_PMAlg
           larreco::RecoAlg_ClusterRecoUtil
           larreco::RecoAlg_CMTool_CMToolBase
           larreco::RecoAlg_ImagePatternAlgs_DataProvider
           ROOT::Core
           ROOT::Physics
           ROOT::Matrix
           ROOT::Minuit
           canvas::canvas
           fhiclcpp::fhiclcpp
           cetlib_except::cetlib_except
        )

add_subdirectory(CMTool)
add_subdirectory(ClusterRecoUtil)
add_subdirectory(Cluster3DAlgs)
add_subdirectory(ImagePatternAlgs)
add_subdirectory(PMAlg)
add_subdirectory(TCAlg)
add_subdirectory(xml)

install_headers()
install_fhicl()
install_source()

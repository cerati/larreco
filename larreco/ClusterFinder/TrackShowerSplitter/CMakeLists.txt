add_subdirectory(Segmentation2D)

simple_plugin(TrackShowerHits   "module"
			lardataobj::RawData
		 	lardataobj::RecoBase
			larreco_RecoAlg
			larreco_ClusterFinder_TrackShowerSplitter_Segmentation2D
		 	larcorealg::Geometry
			larcore::Geometry_Geometry_service
			lardata::Utilities
               art::Framework_Core
			art::Framework_Principal
			art::Framework_Services_Registry
         		art_root_io::tfile_support ROOT::Core
    			art_root_io::TFileService_service
 			art::Persistency_Common
			art::Persistency_Provenance
			art::Utilities
			canvas::canvas
			messagefacility::MF_MessageLogger
			cetlib::cetlib cetlib_except::cetlib_except
		        ROOT::Core ROOT::Hist
)

install_headers()
install_fhicl()
install_source()
install_scripts()

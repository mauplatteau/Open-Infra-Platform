#
#    Copyright (c) 2018 Technical University of Munich
#    Chair of Computational Modeling and Simulation.
#
#    TUM Open Infra Platform is free software; you can redistribute it and/or modify
#    it under the terms of the GNU General Public License Version 3
#    as published by the Free Software Foundation.
#
#    TUM Open Infra Platform is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
#    GNU General Public License for more details.
#
#    You should have received a copy of the GNU General Public License
#    along with this program. If not, see <http://www.gnu.org/licenses/>.
#

add_definitions(-DBLUEINFRASTRUCTURE_EXPORT)
set(CMAKE_DEBUG_POSTFIX "d")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG 	../Debug)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE 	../Release)
set(CMAKE_PDB_OUTPUT_DIRECTORY_DEBUG 	    ../Debug)
set(CMAKE_PDB_OUTPUT_DIRECTORY_RELEASE 	    ../Release)

# Unicode rules!
add_definitions(-D_UNICODE)
add_definitions(-DNOMINMAX)
add_definitions(-D_UNICODE -DBOOST_PYTHON_STATIC_LIB)
add_definitions(-DRAPTOR_STATIC)

#file(GLOB OpenInfraPlatform_Infrastructure_Alignment_HorizontalAlignment_Source 	src/OpenInfraPlatform/Infrastructure/Alignment/HorizontalAlignment/*.*)								
#file(GLOB OpenInfraPlatform_Infrastructure_Alignment_Source 						src/OpenInfraPlatform/Infrastructure/Alignment/*.*)			
#file(GLOB OpenInfraPlatform_Infrastructure_Alignment_VerticalAlignment_Source 		src/OpenInfraPlatform/Infrastructure/Alignment/VerticalAlignment/*.*)			
#file(GLOB OpenInfraPlatform_Infrastructure_Bindings_Source 							src/OpenInfraPlatform/Infrastructure/Bindings/*.*)		
file(GLOB OpenInfraPlatform_Infrastructure_Core_Source 								src/OpenInfraPlatform/Infrastructure/Core/*.*)	
#file(GLOB OpenInfraPlatform_Infrastructure_CrossSection_Source 						src/OpenInfraPlatform/Infrastructure/CrossSection/*.*)			
file(GLOB OpenInfraPlatform_Infrastructure_DigitalElevationModel_Source 			src/OpenInfraPlatform/Infrastructure/DigitalElevationModel/*.*)
#file(GLOB OpenInfraPlatform_Infrastructure_SectionedSolid_Source 					src/OpenInfraPlatform/Infrastructure/SectionedSolid/*.*)
file(GLOB OpenInfraPlatform_Infrastructure_Girder_Source 							src/OpenInfraPlatform/Infrastructure/Girder/*.*)
file(GLOB OpenInfraPlatform_Infrastructure_SlabField_Source 						src/OpenInfraPlatform/Infrastructure/SlabField/*.*)
file(GLOB OpenInfraPlatform_Infrastructure_Tessellation_Source 						src/OpenInfraPlatform/Infrastructure/Tessellation/*.*)
file(GLOB OpenInfraPlatform_Infrastructure_ProxyModel_Source 				        src/OpenInfraPlatform/Infrastructure/ProxyModel/*.*)	
#file(GLOB OpenInfraPlatform_Infrastructure_EnergyConsumption_Source 				src/OpenInfraPlatform/Infrastructure/EnergyConsumption/*.*)						
#file(GLOB OpenInfraPlatform_Infrastructure_EnergyConsumption_Calculators_Source 	src/OpenInfraPlatform/Infrastructure/EnergyConsumption/Calculators/*.*)	
#file(GLOB OpenInfraPlatform_Infrastructure_EnergyConsumption_Calculators_Parameters_Source 	src/OpenInfraPlatform/Infrastructure/EnergyConsumption/Calculators/Parameters/*.*)	
#file(GLOB OpenInfraPlatform_Infrastructure_EnergyConsumption_Profiles_Source 		src/OpenInfraPlatform/Infrastructure/EnergyConsumption/Profiles/*.*)	
#file(GLOB OpenInfraPlatform_Infrastructure_Export_Source 							src/OpenInfraPlatform/Infrastructure/Export/*.*)		
#file(GLOB OpenInfraPlatform_Infrastructure_IfcPL_Source 							src/OpenInfraPlatform/Infrastructure/IfcPL/*.*)		
#file(GLOB OpenInfraPlatform_Infrastructure_Import_Source 							src/OpenInfraPlatform/Infrastructure/Import/*.*)		
#file(GLOB OpenInfraPlatform_Infrastructure_PointCloudProcessing_Source				src/OpenInfraPlatform/Infrastructure/PointCloudProcessing/*.*)	06.05.19 moved to pcp module (coetzee)
file(GLOB OpenInfraPlatform_Infrastructure_Railway_Source							src/OpenInfraPlatform/Infrastructure/Railway/*.*)										
file(GLOB OpenInfraPlatform_Infrastructure_Source 									src/OpenInfraPlatform/Infrastructure/*.*)	

source_group(OpenInfraPlatform\\Infrastructure										FILES ${OpenInfraPlatform_Infrastructure_Source})
#source_group(OpenInfraPlatform\\Infrastructure\\Alignment							FILES ${OpenInfraPlatform_Infrastructure_Alignment_Source})			
#source_group(OpenInfraPlatform\\Infrastructure\\Alignment\\HorizontalAlignment		FILES ${OpenInfraPlatform_Infrastructure_Alignment_HorizontalAlignment_Source})								
#source_group(OpenInfraPlatform\\Infrastructure\\Alignment\\VerticalAlignment		FILES ${OpenInfraPlatform_Infrastructure_Alignment_VerticalAlignment_Source})													
#source_group(OpenInfraPlatform\\Infrastructure\\Bindings							FILES ${OpenInfraPlatform_Infrastructure_Bindings_Source})			
source_group(OpenInfraPlatform\\Infrastructure\\Core								FILES ${OpenInfraPlatform_Infrastructure_Core_Source})		
#source_group(OpenInfraPlatform\\Infrastructure\\CrossSection						FILES ${OpenInfraPlatform_Infrastructure_CrossSection_Source})				
source_group(OpenInfraPlatform\\Infrastructure\\DigitalElevationModel  				FILES ${OpenInfraPlatform_Infrastructure_DigitalElevationModel_Source})						
source_group(OpenInfraPlatform\\Infrastructure\\ProxyModel 				            FILES ${OpenInfraPlatform_Infrastructure_ProxyModel_Source})
#source_group(OpenInfraPlatform\\Infrastructure\\SectionedSolid						FILES ${OpenInfraPlatform_Infrastructure_SectionedSolid_Source})
source_group(OpenInfraPlatform\\Infrastructure\\Girder  							FILES ${OpenInfraPlatform_Infrastructure_Girder_Source})
source_group(OpenInfraPlatform\\Infrastructure\\SlabField  							FILES ${OpenInfraPlatform_Infrastructure_SlabField_Source})
source_group(OpenInfraPlatform\\Infrastructure\\Tessellation  						FILES ${OpenInfraPlatform_Infrastructure_Tessellation_Source})
#source_group(OpenInfraPlatform\\Infrastructure\\EnergyConsumption					FILES ${OpenInfraPlatform_Infrastructure_EnergyConsumption_Source})
#source_group(OpenInfraPlatform\\Infrastructure\\EnergyConsumption\\Calculators 		FILES ${OpenInfraPlatform_Infrastructure_EnergyConsumption_Calculators_Source_Source})
#source_group(OpenInfraPlatform\\Infrastructure\\EnergyConsumption\\Calculators\\Parameters_Source 	FILES ${OpenInfraPlatform_Infrastructure_EnergyConsumption_Calculators_Parameters_Source})
#source_group(OpenInfraPlatform\\Infrastructure\\EnergyConsumption\\Profiles 		FILES ${OpenInfraPlatform_Infrastructure_EnergyConsumption_Profiles_Source})
#source_group(OpenInfraPlatform\\Infrastructure\\Export								FILES ${OpenInfraPlatform_Infrastructure_Export_Source})		
#source_group(OpenInfraPlatform\\Infrastructure\\IfcPL								FILES ${OpenInfraPlatform_Infrastructure_IfcPL_Source})		
#source_group(OpenInfraPlatform\\Infrastructure\\Import								FILES ${OpenInfraPlatform_Infrastructure_Import_Source})		
#source_group(OpenInfraPlatform\\Infrastructure\\PointCloudProcessing				FILES ${OpenInfraPlatform_Infrastructure_PointCloudProcessing_Source})	06.05.19 moved to pcp module (coetzee)		
source_group(OpenInfraPlatform\\Infrastructure\\Railway								FILES ${OpenInfraPlatform_Infrastructure_Railway_Source})				

include_directories(
	${Boost_INCLUDE_DIR} 
	#${PYTHON_INCLUDE_DIRS}
	#${VLD_INCLUDE_DIR}
	${BLUEFRAMEWORK_INCLUDE_DIR}
	${EIGEN3_INCLUDE_DIR}
	src
	#${LIBLAS_INCLUDE_DIRS}	06.05.19 moved to pcp module (coetzee)
	../external/QtXlsxWriter/src/xlsx	
	${OKLABI_ROOT_DIR}/Kern-C++
	${OKLABI_ROOT_DIR}/Dienst
	${QHULL_INCLUDE_DIRS}
	${RAPTOR2_INCLUDE_DIRS}
	
	#Experimental
	${visit_struct_INCLUDE_DIR}
	#${OpenInfraPlatform.EarlyBinding_INCLUDE_DIR}
	#${CC_INCLUDE_DIRS}	06.05.19 moved to pcp module (coetzee)
)

# Create a target for the library
add_library(OpenInfraPlatform.Infrastructure SHARED 
	#${OpenInfraPlatform_Infrastructure_Alignment_HorizontalAlignment_Source}
	#${OpenInfraPlatform_Infrastructure_Alignment_Source}
	#${OpenInfraPlatform_Infrastructure_Alignment_VerticalAlignment_Source}
	#${OpenInfraPlatform_Infrastructure_Bindings_Source}
	${OpenInfraPlatform_Infrastructure_Core_Source}
	#${OpenInfraPlatform_Infrastructure_CrossSection_Source}
	${OpenInfraPlatform_Infrastructure_DigitalElevationModel_Source}
	${OpenInfraPlatform_Infrastructure_ProxyModel_Source}
	#${OpenInfraPlatform_Infrastructure_SectionedSolid_Source}
	${OpenInfraPlatform_Infrastructure_Girder_Source}
	${OpenInfraPlatform_Infrastructure_SlabField_Source}
	${OpenInfraPlatform_Infrastructure_Tessellation_Source}
	#${OpenInfraPlatform_Infrastructure_EnergyConsumption_Source}
	#${OpenInfraPlatform_Infrastructure_EnergyConsumption_Calculators_Source_Source}
	#${OpenInfraPlatform_Infrastructure_EnergyConsumption_Calculators_Parameters_Source}
	#${OpenInfraPlatform_Infrastructure_EnergyConsumption_Profiles_Source}
	#${OpenInfraPlatform_Infrastructure_Export_Source}
	#${OpenInfraPlatform_Infrastructure_IfcPL_Source}
	#${OpenInfraPlatform_Infrastructure_Import_Source}
	#${OpenInfraPlatform_Infrastructure_PointCloudProcessing_Source}	06.05.19 moved to pcp module (coetzee)
	${OpenInfraPlatform_Infrastructure_Railway_Source}
	${OpenInfraPlatform_Infrastructure_Source}
)

target_link_libraries( OpenInfraPlatform.Infrastructure
		OpenInfraPlatform.EarlyBinding
		#${OpenInfraPlatform.EarlyBinding_LIBRARIES}
		# Boost
		${Boost_LIBRARIES}		
		# BlueFramework
		${BLUEFRAMEWORK_LIBRARIES}	
		# Python
		#${PYTHON_LIBRARIES}
		# External libs
		QtXlsxWriter
		#${LIBLAS_LIBRARIES}	06.05.19 moved to pcp module (coetzee)
		# Oklabi
		${OKLABI_LIBRARIES}
		#
		${QHULL_STATIC_LIBRARIES}
		# Raptor
		${RAPTOR2_LIBRARIES}
		# EXPRESS Binding for Meta model
		#OpenInfraPlatform.ExpressBinding
		Rpcrt4.lib
		#${CC_LIBRARIES}	06.05.19 moved to pcp module (coetzee)
	)
# Use the Widgets module from Qt 5.
target_link_libraries(OpenInfraPlatform.Infrastructure Qt5::Xml Qt5::XmlPatterns Qt5::Gui Qt5::OpenGL)

# Install.
install(TARGETS OpenInfraPlatform.Infrastructure   
   RUNTIME DESTINATION bin
   COMPONENT oip_runtime
)

install(TARGETS OpenInfraPlatform.Infrastructure   
   ARCHIVE DESTINATION lib
   COMPONENT oip_import_libs
)

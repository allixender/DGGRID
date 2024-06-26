cmake_minimum_required (VERSION 3.9)

add_library(dglib
  lib/DgAddressBase.cpp
  lib/DgAddressType.cpp
  lib/DgApSeq.cpp
  lib/DgBase.cpp
  lib/DgBoundedHexC2RF2D.cpp
  lib/DgBoundedHexC3C2RF2D.cpp
  lib/DgBoundedHexC3RF2D.cpp
  lib/DgBoundedIDGG.cpp
  lib/DgBoundedIDGGS.cpp
  lib/DgBoundedRF2D.cpp
  lib/DgBoundedRFBase0.cpp
  lib/DgBoundedRF.hpp
  lib/DgBoundedRFS2D.cpp
  lib/DgCell.cpp
  lib/DgColor.cpp
  lib/DgConverterBase.cpp
  lib/DgDataFieldBase.cpp
  lib/DgDataList.cpp
  lib/DgDiscRF.hpp
  lib/DgDiscRFS2D.cpp
  lib/DgDiscRFS.hpp
  lib/DgDistanceBase.cpp
  lib/DgDmdD4Grid2D.cpp
  lib/DgDmdD4Grid2DS.cpp
  lib/DgDmdD8Grid2D.cpp
  lib/DgDmdD8Grid2DS.cpp
  lib/DgDmdIDGG.cpp
  lib/DgDVec2D.cpp
  lib/DgDVec3D.cpp
  lib/DgEllipsoidRF.cpp
  lib/DgGeoSphRF.cpp
  lib/DgGridTopo.cpp
  lib/DgHexC1Grid2D.cpp
  lib/DgHexC2Grid2D.cpp
  lib/DgHexC3Grid2D.cpp
  lib/DgHexGrid2DS.cpp
  lib/DgHexIDGG.cpp
  lib/DgHexIDGGS.cpp
  lib/DgIcosaMap.cpp
  lib/DgIDGGBase.cpp
  lib/DgIDGG.cpp
  lib/DgIDGGS3H.cpp
  lib/DgIDGGS43H.cpp
  lib/DgIDGGS4D.cpp
  lib/DgIDGGS4H.cpp
  lib/DgIDGGS7H.cpp
  lib/DgIDGGS4T.cpp
  lib/DgIDGGSBase.cpp
  lib/DgIDGGS.cpp
  lib/DgIDGGutil.cpp
  lib/DgInAIGenFile.cpp
  lib/DgInGdalFile.cpp
  lib/DgInLocStreamFile.cpp
  lib/DgInLocTextFile.cpp
  lib/DgInputStream.cpp
  lib/DgInShapefileAtt.cpp
  lib/DgInShapefile.cpp
  lib/DgIVec2D.cpp
  lib/DgIVec3D.cpp
  lib/DgLocation.cpp
  lib/DgLocBase.cpp
  lib/DgLocList.cpp
  lib/DgLocVector.cpp
  lib/DgOutAIGenFile.cpp
  lib/DgOutChildrenFile.cpp
  lib/DgOutGdalFile.cpp
  lib/DgOutGeoJSONFile.cpp
  lib/DgOutKMLfile.cpp
  lib/DgOutLocFile.cpp
  lib/DgOutLocTextFile.cpp
  lib/DgOutNeighborsFile.cpp
  lib/DgOutPRCellsFile.cpp
  lib/DgOutPRPtsFile.cpp
  lib/DgOutPtsText.cpp
  lib/DgOutputStream.cpp
  lib/DgOutRandPtsText.cpp
  lib/DgOutShapefile.cpp
  lib/DgPhysicalRF2D.hpp
  lib/DgPhysicalRFBase.hpp
  lib/DgPhysicalRF.hpp
  lib/DgPhysicalRFS2D.hpp
  lib/DgPolygon.cpp
  lib/DgProjFuller.cpp
  lib/DgProjGnomonicRF.cpp
  lib/DgProjISEA.cpp
  lib/DgProjTriRF.cpp
  lib/DgRandom.cpp
  lib/DgRFBase.cpp
  lib/DgRF.hpp
  lib/DgRFNetwork.cpp
  lib/DgSeriesConverter.cpp
  lib/DgSqrD4Grid2D.cpp
  lib/DgSqrD4Grid2DS.cpp
  lib/DgSqrD8Grid2D.cpp
  lib/DgSqrD8Grid2DS.cpp
  lib/DgSuperfund.cpp
  lib/DgTriGrid2D.cpp
  lib/DgTriGrid2DS.cpp
  lib/DgTriIDGG.cpp
  lib/DgUtil.cpp
  lib/DgZ3RF.cpp
  lib/DgZ3StringRF.cpp
  lib/DgZOrderRF.cpp
  lib/DgZOrderStringRF.cpp
)

if(GDAL_FOUND)
  target_compile_definitions(dglib PRIVATE USE_GDAL)
endif()

# If GDAL isn't present than ${GDAL_INCLUDE_DIRS} and ${GDAL_LIBRARIES} give
# empty strings
target_include_directories(dglib PUBLIC include ${GDAL_INCLUDE_DIRS})
target_link_libraries(dglib PRIVATE ${GDAL_LIBRARIES} shapelib proj4lib)
target_compile_features(dglib PRIVATE cxx_std_11)

# Convert to SBB data to same SRID (EPSG 2056) & geopackage

ogr2ogr -t_srs EPSG:2056 -s_srs EPSG:21781 -f GPKG parcels.gpkg -nlt MULTIPOLYGON GIS_SBB_PVA_SDach_Hackathon_Raum/40_SBB_PVA_SDach_Hackathon_Raum.shp

# Clean up input GeoJSON by removing unparsable 'Infinity'

sed -i '' 's/Infinity/0.0/g' solar_new_properties_added.geojson

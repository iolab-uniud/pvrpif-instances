# Instances for the Periodic Vehicle Routing with Intermediate Facilities: Waste Collection
Case study and artificial Instances for the asymmetric periodic vehicle routing problems designed according to the requirements of  a waste collection company.

The data is organized in [GeoJson](https://it.wikipedia.org/wiki/GeoJSON) files, the info entry contains all the information required for the 
vehicles, e.g. size of the fleet, and the planning, e.g.  planning Horizon. The information on the nodes, the customers, is within the features entry. 

```
{"type": "FeatureCollection",
 "info": { "numVehicles": 2, ...},
 "features": [
               {
                "id": "0",
                "type": "Feature",
                "properties": {"id": 0, "type": "depot",...},
                "geometry": {"type": "Point", "coordinates":..}
               },
              ...
]}
```

It is recommended that the following libraries be used for the reading of the instances:
- C++: [nlohmann](https://github.com/nlohmann/json)
- Python: [json package](https://docs.python.org/3/library/json.html)

It is recommended that the following library be used for the visualizing the instances:
- Python: [geopandas](https://geopandas.org/en/stable/)

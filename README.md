# Instances for the Periodic Vehicle Routing with Intermediate Facilities: Waste Collection
Case study and artificial Instances for the asymmetric periodic vehicle routing problems with intermediate facilities (PVRP-IF, [Angelelli and Speranza](https://doi.org/10.1016/S0377-2217(01)00206-5) ) designed according to the requirements of  a waste collection company.
Authors: [Francesco Taverna](https://dmif.uniud.it/it/didattica/dottorato/iai/dottorandi/francesco-taverna), [Christian Tilk](https://busan.univie.ac.at/members/members-of-research-group-prescriptive-business-analytics/ass-prof-dr-christian-tilk/).

## Naming Convention
The naming of the instances follows the scheme, *Area*\_*Number of customers*\_*Planning Horizon*\_*Instance number*, where the latter distinguishes between different instances that share the same number of customers and planning horizon. 

For example:  **`Milano_020_4_0.geojson`**  
- *Milano*: the area where the instance is located  
- *020*: the instance includes 20 customers  
- *4*: the planning horizon spans 4 days  
- *0*: this is the 0th instance among those with 20 customers and a 4-day planning horizon

## Structure of the instances
The data is organized in [GeoJson](https://it.wikipedia.org/wiki/GeoJSON) files, the info entry contains all the information required for the 
vehicles, e.g. size of the fleet, and the planning, e.g.  planning Horizon. The information on the nodes, i.e., depot, customers, and intermediate facilities, is within the features entry. 
Moreover, the travel time matrix ([[int]]) is stored in the duration entry,  and for the case study the adjacency matrix ([[bool]])  in the adjacency entry.
The travel time is the actual road time and is calculated by [OSRM](https://project-osrm.org/) using the [OSM](https://www.openstreetmap.org/)'s road layout. 

```json
{"type": "FeatureCollection",
 "info": { "numVehicles": 2, ...},
 "features": [
               {
                "id": "0",
                "type": "Feature",
                "properties": {"id": 0, "type": "depot",...},
                "geometry": {"type": "Point", "coordinates":[...]}
               },
              ...
]
"duration": [[....],[....],]
}
```
> **Note:**
> The coordinates of the customers in the case study are not provided, namely are all set equal to [0,0].

## To read the instances
It is recommended that the following libraries be used for the reading of the instances:
- C++: [nlohmann](https://github.com/nlohmann/json)
- Python: [json package](https://docs.python.org/3/library/json.html)

## To display the instances
To display the instances it is recommended to use the following library:
- Python: [geopandas](https://geopandas.org/en/stable/)
<p align="center"  >
  <img width="500" height="500" src="instanceExample.png"/>
  <figcaption>The figure illustrates one of the instances. The red dots represent the bins, while the blue and green dots represent the depot and intermediate facilities respectively.</figcaption>
</p>

## To generate new instances



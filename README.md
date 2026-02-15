## Overview
This notebook uses OpenStreetMap (OSM) data to analyze and visualize the road network in Riyadh city center, then compares multiple routing algorithms between two downtown points of interest.

## Dataset
Source: OpenStreetMap (OSM) via the osmnx Python package
Data type: Road network graph (nodes/edges) with geographic coordinates and edge lengths (meters)
Study area: Riyadh downtown (loaded using a point + radius to avoid large Overpass queries)

## Tools / Libraries

osmnx for downloading and handling OSM road networks
geopandas / matplotlib for spatial plotting
optalgotools for search algorithms and route rendering (BFS, DFS, Dijkstra, Node, draw_route, cost)
pandas for result comparison tables

## In the Notebook
1) Built the Riyadh Downtown Road Network
-Selected two downtown POIs (Saudi Arabia): Al Masmak Fortress & Al Murabba area
-Created a road network around the midpoint of these POIs
-Snapped each POI to the nearest network nodes using nearest_nodes

2) Visualized the Spatial Data in Multiple Formats
-We generated multiple map styles to understand the structure of the city center road network, including:
 Road network plot
 Road type (“highway”) classification map
-Density-style visualization (e.g., hexbin / clustering-style views depending on the cell used)
-Segment length patterns (short segments concentrated in the dense core; long segments mainly on major corridors)

3) Routed Between Two POIs (Algorithm Comparison)
-We computed routes between the two POIs using:
 BFS (unweighted, fewest edges)
 DFS (first-found path, depends on traversal order)
 Dijkstra (weighted shortest path by distance in meters)
 Simulated Annealing (metaheuristic refinement starting from Dijkstra)
-For each method, we reported:
 Cost (route length in meters)
 Process time
 Memory/space estimate

## How to Run

-Install dependencies (if needed):
 !pip install osmnx optalgotools geopandas matplotlib pandas networkx
-Run notebook cells in order:
-Build graph → visualize → define POIs → run algorithms → compare results

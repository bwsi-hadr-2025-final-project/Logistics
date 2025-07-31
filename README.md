#  Disaster Response (2025)

This project is part of an emergency response simulation for a hurricane event in Massachusetts. The **Logistics Team** is responsible for designing a network for distributing emergency resources to hospitals and shelters.

## Team Role: Logistics

Our goals:

- Convert the road grid into a routable network
- Compute travel times using transport scores
- Select & allocate 150,000 resource units to up to 5 distribution centers (DCs)
- Pre-position 40 trucks with realistic capacity constraints
- Route trucks from DCs to shelters and hospitals (within 12 hours travel time)
- Ensure full demand is satisfied (500 units/hospital, 200 units/shelter)
- Collaborate with Planning Team to avoid flood zones using forecast data
- Visualize spatial data using basemaps, OSMnx, and Matplotlib

---

## Files and Data Sources

| File | Description |
|------|-------------|
| `game_grid_2025.geojson` | Base transportation grid with transport scores |
| `Hospitals_2025.geojson` | Location of hospitals and their demand |
| `Shelters_2025.geojson` | Location of shelters and their demand |
| `day1_forecasts_2025.geojson` | Day 1 forecast |
| `day1_track_past.geojson` | Hurricane track |
| `distribution_centers.geojson` | Locations of DCs and allocation |

---

##  Methodology

### Routing Network Construction

- Each grid cell is a node.
- Edges are added only to adjacent cells.
- Edge travel time is calculated as: ```T(x, y) = 20 / (x.transport_score + y.transport_score)```
- We use `GeoPandas` + `NetworkX` for spatial network modeling.

### Basemap + Spatial Data

- We use `contextily` to visualize maps with OpenStreetMap tiles.
- All geometries reprojected to EPSG:3857 for accuracy.

### Resource Allocation & Truck Routing

- 5 DCs selected.
- 150,000 units pre-allocated across DCs.
- Truck pre-positioning and post-storm routing are being planned using shortest paths on the grid network.

---

## Key Libraries

```
geopandas
networkx
matplotlib
contextily
osmnx
shapely
pandas
```
## Installation

```bash
pip install geopandas networkx matplotlib contextily osmnx shapely pandas
```

## Example Visualization
<img width="400" height="458" alt="image" src="https://github.com/user-attachments/assets/ee1851d4-d73b-4845-874c-18440da83418" />
<p><em>Distribution center locations and forecasted hurricane path (the polygon) overlayed on the population distribution of the region</em></p>

---

## Logistics Team — Hurricane Sim 2025

---

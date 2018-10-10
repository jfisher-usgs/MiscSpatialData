# Ackerman Model

Ackerman, D.J., Rousseau, J.P., Rattray, G.W., and Fisher, J.C., 2010,
Steady-state and transient models of groundwater flow and advective
transport, Eastern Snake River Plain aquifer, Idaho National Laboratory and
vicinity, Idaho: U.S. Geological Survey Scientific Investigations Report
2010-5123, 220 p., <https://pubs.usgs.gov/sir/2010/5123/>.

## Data Sets

- *actmodclp* is the polygon used to clip the active model cells from the model grid.
- *inlmodext* is the areal extent of the active model cells in the top model layer.

## Shapefile to GeoJSON Conversion

```r
setwd("./shapefiles")
actmodclp <- rgdal::readOGR(".", "actmodclp")
inlmodext <- rgdal::readOGR(".", "inlmodext")
actmodclp <- sp::spTransform(actmodclp, sp::CRS("+init=epsg:4326"))
inlmodext <- sp::spTransform(inlmodext, sp::CRS("+init=epsg:4326"))
setwd("..")
rgdal::writeOGR(actmodclp, "actmodclp.geojson", layer = "actmodclp", driver = "GeoJSON")
rgdal::writeOGR(inlmodext, "inlmodext.geojson", layer = "inlmodext", driver = "GeoJSON")
```

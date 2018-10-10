# Ackerman Model

Ackerman, D.J., Rousseau, J.P., Rattray, G.W., and **Fisher, J.C.**, 2010,
Steady-state and transient models of groundwater flow and advective
transport, Eastern Snake River Plain aquifer, Idaho National Laboratory and
vicinity, Idaho:, U.S. Geological Survey Scientific Investigations Report
2010-5123, 220 p., <https://pubs.usgs.gov/sir/2010/5123/>.

## Data Sets

- *actmodclp* is the polygon used to clip the active model cells from the model grid.
- *inlmodext* is the areal extent of the active model domain in layer 1.

## Shapefile to GeoJSON Conversion

```r
setwd("./MiscSpatialData/ackerman/shapefiles")
actmodclp <- rgdal::readOGR(getwd(), "actmodclp", verbose = FALSE, integer64 = "allow.loss")
inlmodext <- rgdal::readOGR(getwd(), "inlmodext", verbose = FALSE, integer64 = "allow.loss")
actmodclp <- sp::spTransform(actmodclp, sp::CRS("+init=epsg:4326"))
inlmodext <- sp::spTransform(inlmodext, sp::CRS("+init=epsg:4326"))
setwd("..")
rgdal::writeOGR(actmodclp, "actmodclp.geojson", layer = "actmodclp", driver = "GeoJSON")
rgdal::writeOGR(inlmodext, "inlmodext.geojson", layer = "inlmodext", driver = "GeoJSON")
```

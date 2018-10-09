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

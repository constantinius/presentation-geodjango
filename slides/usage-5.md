##  Usage

Reading geospatial data sources (e.g
[World Borders](http://thematicmapping.org/downloads/world_borders.php))

```Python
>>> from countries import models
>>> from django.contrib.gis.gdal import DataSource
>>> from django.contrib.gis.geos import (
...     GEOSGeometry, Polygon, MultiPolygon
... )
>>> ds = DataSource('path/to/TM_WORLD_BORDERS_SIMPL-0.3.shp')
>>> layer = ds[0]
>>> for feature in layer:
...     geom = GEOSGeometry(feature.geom.wkt)
...     if isinstance(geom, Polygon):
...         geom = MultiPolygon(geom)
...     models.Country.objects.create(
...         name=feature.get("NAME"),
...         border=geom
...     )
...
```

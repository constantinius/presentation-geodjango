##  Usage

    $ python manage.py shell

```Python
>>> from django.contrib.gis.geos import Polygon
>>> from countries import models
>>>
>>> qs = models.City.objects.filter(
...     center__intersects=Polygon.from_bbox((10, 10, 50, 50))
... )
>>> qs[0].center.wkt
u'POINT (16.3599999999999994 48.2000000000000028)'
>>>
```

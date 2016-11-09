##  Usage

    $ python manage.py shell

```Python
>>> from django.contrib.gis.geos import Point, Polygon, MultiPolygon
>>> from countries import models
>>> austria = models.Country.objects.create(
...     name="Austria", border=MultiPolygon(Polygon( ... ))
>>> )
>>> models.City.objects.create(
...     name="Vienna", center=Point(16.36, 48.2), country=austria
... )
```

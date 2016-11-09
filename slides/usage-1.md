##  Usage

    $ django-admin startproject geodjango
    $ cd geodjango
    $ python manage.py startapp countries

`models.py` (See [full documentation](https://docs.djangoproject.com/en/1.10/ref/contrib/gis/model-api/))

```Python
from django.contrib.gis.db import models

class Country(models.Model):
    name = models.CharField(max_length=50)
    border = models.MultiPolygonField()

    objects = models.GeoManager() # deprecated since Django 1.9

class City(models.Model):
    name = models.CharField(max_length=50)
    center = models.PointField()
    country = models.ForeignKey(Country, related_name="cities")

    objects = models.GeoManager() # deprecated since Django 1.9
```

    $ python manage.py migrate

##  Usage

```Python
>>> qs = models.Country.objects.filter(
...     border__intersects=Polygon.from_bbox((10, 10, 50, 50))
... )
>>> for country in qs:
...     print country.name
Algeria
Azerbaijan
Albania
Armenia
Bosnia and Herzegovina
Bulgaria
...
```

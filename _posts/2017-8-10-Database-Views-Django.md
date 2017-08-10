---
layout: post
title: Database Views With Django
published: true
---

In the Django ORM, a database table is tied to a Django ORM model, but it is also possible to tie a database view with a Django ORM model. By doing so, you can hide the data aggregation logic on the database level (in view creating SQL). And most of the ORM features, like double underscore foreign key lookup, still work for the model tied to a database view.

### The Regular Models:

This example uses the following regular models. Each model has a database table tied to it.
```
from django.db import models


class Graph(models.Model):
    user_id = models.CharField(db_column='USER_ID', primary_key=True, max_length=20)
    date = models.DateField(db_column='DATE')
    product = models.DecimalField(db_column='PRODUCT', max_digits=35, decimal_places=2)
    
    class Meta:
        managed = False
        db_table = 'NET_PRODUCT_WISE'
 ```

The graph model is used to store the data used to populate the graph. It has a foreignkey to the user_id model.

### The Database View

The database view is created by following the SQL and it can be injected into a customized data migration with the raw SQL execution command.

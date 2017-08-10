---
layout: post
title: Database Views With Django
published: true
---

Sometimes using database views rather than database tables can be very helpful for querying aggregated data. Typically in the Django ORM, a database table is tied to a Django ORM model, but we found it is also possible to tie a database view with a Django ORM model. By doing so, you can hide the data aggregation logic on the database level (in view creating SQL). And most of the ORM features, like double underscore foreign key lookup, still work for the model tied to a database view. In this blogpost, I’ll walk you through a simple example to illustrate how.

The regular models:
This example uses the following regular models. Each model has a database table tied to it.

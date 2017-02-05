
{% if page.path contains '_posts' %}
  <link rel="amphtml" href="{{ page.id | prepend: '/YOURDIR' | prepend: site.baseurl | prepend: site.url }}">
{% endif %}


---
layout: post
title: "Hello World !"
published: true
---
```python
print "A simple Hello could lead to a million things."
```

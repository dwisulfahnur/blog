---
layout: post
title: "Django SlugField Auto Generate and Unique"
date: 2019-02-09
description: Django SlugField Auto Generate and Unique
image: /assets/images/Django-SlugField.png
author: Dwi Sulfahnur
tags:
  - Django
  - Django-models
  - Slug
---


# Django SlugField Auto Generate and Unique

This is my code when using SlugField on Django with autogenerate when the data created in the first time and it will be unique.

This is my code when using SlugField on Django with autogenerate when the data created in the first time and it will be unique.

```
from django.db import models
from django.utils.text import slugify


class MyModel(models.Model):
    name = models.CharField()
    slug = models.SlugField(unique=True, null=False)
    def _generate_unique_slug(self)
        unique_slug = slugify(self.name)
        num = 1
        while MyModel.objects.filter(slug=unique_slug).exists():
            slug = '{}-{}'.format(unique_slug, num)
            num += 1
            return unique_slug
    def save(self, *args, **kwargs):
        if not self.slug:
            self.slug = self._get_unique_slug()
        super().save(*args, **kwargs)
```

😉


[Canonical link](https://medium.com/@dwisulfahnur/django-slugfield-auto-generate-and-unique-ffaff2043bb3)

Exported from [Medium](https://medium.com) on April 6, 2019.
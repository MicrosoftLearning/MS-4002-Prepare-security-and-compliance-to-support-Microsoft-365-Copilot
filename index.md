---
title: Online Hosted Instructions
permalink: index.html
layout: home
---

# Content Directory

These labs support [MS-4002: Prepare security and compliance to support Microsoft 365 Copilot](https://learn.microsoft.com/training/courses/ms-4002).

Required lab files can be [downloaded here]({{ site.github.repository_url }}/archive/refs/heads/master.zip).

> **Note**: These exercises require a Microsoft 365 lab tenant and accounts provided by your lab hosting provider. Follow the tenant setup instructions in the first exercise.

## Labs

{% assign labs = site.pages | where_exp: "page", "page.url contains '/Instructions/Labs/'" | where_exp: "page", "page.lab.title" | sort: "path" %}
| Lab |
| --- |
{% for activity in labs %}| [{{ activity.lab.title }}]({{ activity.url | relative_url | uri_escape }}) |
{% endfor %}

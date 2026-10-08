---
layout: single
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

- [Home]({{ '/' | relative_url }})
- [Research]({{ '/research/' | relative_url }})
{% for project in site.data.research %}
- [{{ project.title }}]({{ project.url | relative_url }})
{% endfor %}
- [Teaching]({{ '/teaching/' | relative_url }})
- [CV]({{ '/cv/' | relative_url }})

A machine-readable [XML sitemap]({{ '/sitemap.xml' | relative_url }}) is also available.

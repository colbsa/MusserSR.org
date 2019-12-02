---
title: Activities Around Camp
layout: page
permalink: /summer/activities
---

{% for program in site.data.summer-activities %}

{% assign include_image = "/img/summer/" | append: program.thumbnail %}

{% include section_card.html image=include_image title=program.name content=program.description %}

{% endfor %}

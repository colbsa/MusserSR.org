---
title: Activities Around Camp
layout: page
permalink: /summer/activities
excerpt: Many traditional summer highlights are available alongside new programs and fun to have.
---

{% for program in site.data.summer-activities %}

{% assign include_image = "/img/summer/" | append: program.thumbnail %}

{% include section_card.html image=include_image alt=program.alt title=program.name content=program.description %}

{% endfor %}

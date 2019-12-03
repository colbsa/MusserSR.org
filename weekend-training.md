---
title: Training Opportunities
layout: page
permalink: /weekend/training
---

Musser Scout Reservation is home to the Nelson Training Center, a multi-functional locale with trainings for the newest youth leader and the most experienced Scouter. Shooting Sports classes, NYLT, Wood Badge, and other training courses are conducted to give your unit the tools they need to offer the best Scouting program possible.

{% for training in site.data.training %}

{% assign include_image = "/img/weekend/" | append: training.thumbnail %}

{% include section_card.html image=include_image title=training.name content=training.description %}

{% endfor %}

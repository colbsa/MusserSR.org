---
title: Training Opportunities
layout: page
permalink: /weekend/training/
excerpt: Shooting Sports classes, NYLT, Wood Badge, and other training courses are conducted to give your unit the tools they need to offer the best Scouting program possible.
---

Musser Scout Reservation is home to the Nelson Training Center, a multi-functional locale with trainings for the newest youth leader and the most experienced Scouter. Shooting Sports classes, NYLT, Wood Badge, and other training courses are conducted to give your unit the tools they need to offer the best Scouting program possible.

{% for training in site.data.training %}

<div class="card my-3">
  <div class="row">
    <div class="col-md-3">
      {% picture thumb /img/weekend/{{training.thumbnail}} --img class="w-100" --alt {{training.alt}} %}
    </div>
    <div class="col-md-9 p-3">
      <div class="card-block px-3">
        <h2 class="card-title">{{training.name}}</h2>
        <p class="card-text">{{training.description}}</p>
        <a href="{{training.link}}" class="btn btn-primary">Learn More &amp; Sign Up</a>
      </div>
    </div>
  </div>
</div>

{% endfor %}

---
title: Training Opportunities
layout: page
permalink: /weekend/training
---

Nelson Training Center at Musser Scout Reservation is where training for youth and adult courses take place, from NYLT, Shooting Sports, and lots of adult leader courses get the tools to make your Scouting Unit the best.

{% for training in site.data.training %}
<div class="card my-3">
  <div class="row">
    <div class="col-md-3">
      {% picture thumb /img/weekend/{{training.thumbnail}} --img class="w-100" %}
    </div>
    <div class="col-md-9 p-3">
      <div class="card-block px-3">
        <h2 class="card-title">{{training.name}}</h2>
        <p class="card-text">{{training.description}}</p>
      </div>
    </div>
  </div>
</div>
{% endfor %}

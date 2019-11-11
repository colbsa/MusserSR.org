---
title: Activities Around Camp
layout: page
permalink: /summer/activities
---

{% for program in site.data.summer-activities %}
<div class="card my-3">
  <div class="row">
    <div class="col-md-3">
      <img src="/img/summer/{{program.thumbnail}}" class="w-100">
    </div>
    <div class="col-md-9 p-3">
      <div class="card-block px-3">
        <h2 class="card-title">{{program.name}}</h2>
        <p class="card-text">{{program.description}}</p>
      </div>
    </div>
  </div>
</div>
{% endfor %}

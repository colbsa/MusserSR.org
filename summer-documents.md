---
title: Important Documents
layout: page
permalink: /summer/documents
excerpt: Flyers, information packets, and forms for summer camp and weekend excursions.
---

<div class="row">
  {%- for section in site.data.documents -%}
  <div class="col-md-6">
    <h2>{{section.name}}</h2>
    <hr>
    <ul>
      {%- for file in section.files %}
        <li>
        {%- if file.url -%}
        <a href="{{file.url}}" target="_blank">{{file.name}}</a>
        {%- else -%}
        {{file.name}} <em>(Coming&nbsp;
        {%- if file.update -%}
        {{file.update | date: "%B %Y"}})
        {%- else -%}
        Soon!)
        {%- endif -%}
        </em>
        {%- endif -%}
        </li>
      {%- endfor %}
    </ul>
  </div>
  {% endfor -%}
</div>

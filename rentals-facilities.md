---
title: Reserve a Facility
layout: page
permalink: /rentals/facilities
---

<table class="table table-striped table-responsive">
  <thead>
    <tr class="text-nowrap">
      <th scope="col">Name</th>
      <th scope="col">Camp</th>
      <th scope="col">Type</th>
      <th scope="col">Cost</th>
      <th scope="col"><abbr title="Capacity">Cap</abbr></th>
      <th scope="col"><abbr title="Adirondacks">Adir</abbr></th>
      <th scope="col">Cots</th>
      <th scope="col"><abbr title="Electricity">Elec</abbr></th>
      <th scope="col">Heat</th>
      <th scope="col">Stove</th>
      <th scope="col"><abbr title="Refrigerator">Ref</abbr></th>
      <th scope="col">Water</th>
      <th scope="col">Restroom</th>
      <th scope="col">Fireplace</th>
      <th scope="col">Pavilion</th>
      <th scope="col">Firepit</th>
      <th scope="col">Parking</th>
      <th scope="col">Cub Friendly</th>
    </tr>
  </thead>
  <tbody>
  {% for facility in site.data.lodging %}
    <tr>
      <td scope="row">{{facility.name}}</td>
      <td>{{facility.camp}}</td>
      <td class="text-nowrap">
        {%- if facility.cabin and facility.site -%}
        <i class="fas fa-home"></i> <i class="fas fa-plus"></i> <i class="fas fa-campground"></i>
        {%- elsif facility.cabin -%}
        <i class="fas fa-home"></i>
        {%- else -%}
        <i class="fas fa-campground"></i>
        {%- endif -%}
      </td>
      <td>&dollar;{{facility.cost}}</td>
      <td>{{facility.capacity}}</td>
      <td>{{facility.adirondacks}}</td>
      <td>{% if facility.cots %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.electricity %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.heat %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{{facility.stove}}</td>
      <td>{% if facility.refrigerator %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{{facility.water}}</td>
      <td>{{facility.restroom}}</td>
      <td>{% if facility.fireplace %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.pavilion %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.firepit %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.parking %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.cubs %}<i class="fas fa-check"></i>{% endif %}</td>
    </tr>
  {%- endfor -%}
  </tbody>
</table>

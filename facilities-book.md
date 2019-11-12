---
title: Reserve a Facility
layout: page
permalink: /rentals/facilities
---

<table class="table table-striped table-responsive">
  <thead>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">Camp</th>
      <th scope="col">Type</th>
      <th scope="col">Cost</th>
      <th scope="col">Capacity</th>
      <th scope="col">Adirondacks</th>
      <th scope="col">Cots</th>
      <th scope="col">Electricity</th>
      <th scope="col">Heat</th>
      <th scope="col">Stove</th>
      <th scope="col">Refrigerator</th>
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
      <td>
        {%- case facility.type -%}
        {%- when "Cabin" -%}
        <i class="fas fa-home"></i>
        {%- when "Tent Site" -%}
        <i class="fas fa-home"></i><i class="fas fa-plus"></i><i class="fas fa-campground"></i>
        {%- else -%}
        <i class="fas fa-campground"></i>
        {%- endcase -%}
      </td>
      <td>&dollar;{{facility.cost}}</td>
      <td>{{facility.capacity}}</td>
      <td>{{facility.adirondacks}}</td>
      <td>{% if facility.cots == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.electricity == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.heat == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{{facility.stove}}</td>
      <td>{% if facility.refrigerator == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{{facility.water}}</td>
      <td>{{facility.restroom}}</td>
      <td>{% if facility.fireplace == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.pavilion == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.firepit == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.parking == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
      <td>{% if facility.cubs == "TRUE" %}<i class="fas fa-check"></i>{% endif %}</td>
    </tr>
  {%- endfor -%}
  </tbody>
</table>

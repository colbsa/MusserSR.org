---
title: Reserve a Facility
layout: page
permalink: /rentals/facilities/
excerpt: Musser Scout Reservation is home to many cabins and campsites available for rental throughout the year.
dependencies:
- src: //cdn.datatables.net/1.10.20/js/jquery.dataTables.min.js
- src: //cdn.datatables.net/1.10.20/js/dataTables.bootstrap4.min.js
scripts: 
- src: assets/custom/js/rentals-facilities.js

---

## Cabins & Campsites
Musser Scout Reservation is home to {{site.data.lodging.size}} cabins and campsites available for rental throughout the year. Review the table below to see the accommodations that are available with each facility. With many different options to choose from, there is something available for any unit - Cub Pack, Scouts BSA Troop, Venturing Crew, or Sea Scout Ship - looking to have an outdoor camping experience. Those facilities that are “Cub Friendly” - with heating and year-round water - are noted as such. All cabins and sites have either a fireplace inside or a fire pit outside. 

{% contentfor sidebar %}

{% picture thumb /img/rentals/campsites/generic_creek.jpg --img class="img-fluid rounded" --alt A dome tent pitched with the entryway facing a small creek with fall foliage on the ground %}

<a class="btn btn-primary btn-block" href="https://campreservation.com/525/Camps/417" target="_blank">Book Now!</a>

{% endcontentfor %}

{% contentfor bottom %}

## Facilities
<table class="table table-striped table-responsive" id="facilitiesTable">
  <thead>
    <tr class="text-nowrap">
      <th scope="col">Name</th>
      <th scope="col">Camp</th>
      <th scope="col"><abbr title="Cabin"><i class="fas fa-home"></i></abbr></th>
      <th scope="col"><abbr title="Campsite"><i class="fas fa-campground"></i></abbr></th>
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
      <th scope="col">Pavilion</th>
      <th scope="col">Parking</th>
      <th scope="col">Cub Friendly</th>
    </tr>
  </thead>
  <tbody>
  {% for facility in site.data.lodging %}
    <tr>
      <td class="text-nowrap" scope="row">{{facility.name}}</td>
      <td>{{facility.camp}}</td>
      <td>{% if facility.cabin %}&check;{% endif %}</td>
      <td>{% if facility.site %}&check;{% endif %}</td>
      <td>&dollar;{{facility.cost}}</td>
      <td>{{facility.capacity}}</td>
      <td>{{facility.adirondacks}}</td>
      <td>{% if facility.cots %}&check;{% endif %}</td>
      <td>{% if facility.electricity %}&check;{% endif %}</td>
      <td>{% if facility.heat %}&check;{% endif %}</td>
      <td>{{facility.stove}}</td>
      <td>{% if facility.refrigerator %}&check;{% endif %}</td>
      <td>{{facility.water}}</td>
      <td>{{facility.restroom}}</td>
      <td>{% if facility.pavilion %}&check;{% endif %}</td>
      <td>{% if facility.parking %}&check;{% endif %}</td>
      <td>{% if facility.cubs %}&check;{% endif %}</td>
    </tr>
  {%- endfor -%}
  </tbody>
  <tfoot>
    <tr class="text-nowrap">
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </tfoot>
</table>

*Full Washroom denotes that a facility has both flush toilets and a shower.*<br>
*Specific information regarding the location of nearby water can be found on our [reservation maps](/maps).*

{% assign delmont_facilities = site.data.lodging | where: "camp", "Delmont" %}
{% assign garrison_facilities = site.data.lodging | where: "camp", "Garrison" %}
{% assign hart_facilities = site.data.lodging | where: "camp", "Hart" %}

{% assign musser_cabins = site.data.lodging | where: "cabin", true %}
{% assign musser_sites = site.data.lodging | where: "site", true %}

{% assign delmont_cabins = delmont_facilities | where: "cabin", true %}
{% assign delmont_sites = delmont_facilities | where: "site", true %}

{% assign garrison_cabins = garrison_facilities | where: "cabin", true %}
{% assign garrison_sites = garrison_facilities | where: "site", true %}

{% assign hart_cabins = hart_facilities | where: "cabin", true %}
{% assign hart_sites = hart_facilities | where: "site", true %}

{% assign delmont_cap = 0 %}
{% for facility in delmont_facilities %}
  {% assign delmont_cap = delmont_cap | plus: facility.capacity %}
{% endfor %}
{% assign garrison_cap = 0 %}
{% for facility in garrison_facilities %}
  {% assign garrison_cap = garrison_cap | plus: facility.capacity %}
{% endfor %}
{% assign hart_cap = 0 %}
{% for facility in hart_facilities %}
  {% assign hart_cap = hart_cap | plus: facility.capacity %}
{% endfor %}

{% assign musser_cap = delmont_cap | plus: garrison_cap | plus: delmont_cap %}

<div class="row">
  <div class="col">
    <h2>Venues</h2>
    <table class="table table-striped table-responsive">
      <thead>
        <tr class="text-nowrap">
          <th scope="col">Name</th>
          <th scope="col">Cost</th>
          <th scope="col"><abbr title="Cabins"><i class="fas fa-home"></i></abbr></th>
          <th scope="col"><abbr title="Campsites"><i class="fas fa-campground"></i></abbr></th>
          <th scope="col"><abbr title="Capacity">Cap</abbr></th>
          <th scope="col">Notes</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td scope="row">Musser Scout Reservation</td>
          <td>&dollar;3400</td>
          <td>{{musser_cabins.size}}</td>
          <td>{{musser_sites.size}}</td>
          <td>{{musser_cap | divided_by: 10 | round | times: 10}}</td>
          <td></td>
        </tr>
        <tr>
          <td scope="row">Camp Delmont</td>
          <td>&dollar;750</td>
          <td>{{delmont_cabins.size}}</td>
          <td>{{delmont_sites.size}}</td>
          <td>{{delmont_cap | divided_by: 10 | round | times: 10}}</td>
          <td></td>
        </tr>
        <tr>
          <td scope="row">Camp Garrison</td>
          <td>&dollar;1000</td>
          <td>{{garrison_cabins.size}}</td>
          <td>{{garrison_sites.size}}</td>
          <td>{{garrison_cap | divided_by: 10 | round | times: 10}}</td>
          <td></td>
        </tr>
        <tr>
          <td scope="row">Camp Hart</td>
          <td>&dollar;1150</td>
          <td>{{hart_cabins.size}}</td>
          <td>{{hart_sites.size}}</td>
          <td>{{hart_cap | divided_by: 10 | round | times: 10}}</td>
          <td>Includes Dining Hall and Kitchen</td>
        </tr>
        <tr>
          <td scope="row">Camp Hart Dining Hall</td>
          <td>&dollar;125</td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <td scope="row">Camp Hart Dining Hall &amp; Kitchen</td>
          <td>&dollar;250</td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <td scope="row">Nelson Training Center</td>
          <td>&dollar;500</td>
          <td>1</td>
          <td>5</td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <td scope="row">Nelson Scouting Ceremony</td>
          <td>&dollar;100</td>
          <td></td>
          <td></td>
          <td></td>
          <td>For an approximately 3 hour ceremony or other event. Not available to book longer than a month in advance.</td>
        </tr>
      </tbody>
    </table>
  </div>
  <div class="col">
    <h2>Special Events</h2>
    Facility and venue prices are listed for Scouting groups and are based on a per weekend rental except where otherwise noted. Our facilities and camp venues are available for non-Scouting groups to rent. For more information on renting any part of Musser Scout Reservation for a special event, visit <a href="/rentals/private-events">Events in Camp</a>.
  </div>
</div>

{% endcontentfor %}

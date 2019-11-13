---
title: Reserve a Facility
layout: page
permalink: /rentals/facilities
scripts: |
  <script src="//cdn.datatables.net/1.10.20/js/jquery.dataTables.min.js"></script>
  <script src="//cdn.datatables.net/1.10.20/js/dataTables.bootstrap4.min.js"></script>
  <script type="text/javascript">
    $(document).ready( function () {
        $('#facilitiesTable').DataTable();
    } );
  </script>

---

<div class="card my-3">
  <div class="row">
    <div class="col-md-3">
      <img src="https://via.placeholder.com/500" class="w-100">
    </div>
    <div class="col-md-9 p-3">
      <div class="card-block px-3">
        <h2 class="card-title">Cabins and Campsites</h2>
        <p class="card-text">Musser Scout Reservation hosts {{site.data.lodging.size}} cabins and campsites available for rental. See their accomodations listed below. Facilities that are "Cub Friendly" are singled out for their heating and availability of water year-round.</p>
        <p>
          <a class="btn btn-primary">Book Now!</a>
        </p>
      </div>
    </div>
  </div>
</div>

## Facilities
<table class="table table-striped table-responsive" id="facilitiesTable">
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
  <tfoot>
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
  </tfoot>
</table>

## Special Event Venues

<table class="table table-striped table-responsive">
  <thead>
    <tr class="text-nowrap">
      <th scope="col">Name</th>
      <th scope="col">Cost</th>
      <th scope="col"><i class="fas fa-home"></i></th>
      <th scope="col"><i class="fas fa-campground"></i></th>
      <th scope="col">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td scope="row">Musser Scout Reservation</td>
      <td>&dollar;3400</td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td scope="row">Camp Delmont</td>
      <td>&dollar;750</td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td scope="row">Camp Garrison</td>
      <td>&dollar;1000</td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td scope="row">Camp Hart</td>
      <td>&dollar;1150</td>
      <td></td>
      <td></td>
      <td>Includes Dining Hall and Kitchen</td>
    </tr>
    <tr>
      <td scope="row">Camp Hart Dining Hall</td>
      <td>&dollar;125</td>
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
    </tr>
    <tr>
      <td scope="row">Nelson Training Center</td>
      <td>&dollar;500</td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td scope="row">Nelson Scouting Ceremony</td>
      <td>&dollar;100</td>
      <td></td>
      <td></td>
      <td>For an approximately 3 hour ceremony or other event. Not available to book longer than a month in advance</td>
    </tr>
  </tbody>
</table>
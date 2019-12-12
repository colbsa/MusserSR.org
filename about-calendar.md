---
title: Event Calendar
layout: page
permalink: /calendar/
excerpt: Stay up to date on all of our upcoming events at Musser Scout Reservation.
---
<div class="table-responsive col-lg-10 offset-lg-1 col-xl-8 offset-xl-2">
  <table class="table table-responsive table-striped mt-3">
    <thead>
      <tr>
        <th scope="col">Event</th>
        <th scope="col">Dates</th>
        <th scope="col">Registration</th>
      </tr>
    </thead>
    <tbody>
      {% for event in site.data.events %}
        <tr>
          <td class="align-middle">{{event.title}}</td>
          <td class="align-middle">
          {% if event.date-end %}
            {% assign m = event.date | date: "%-m" %}
            {% assign n = event.date-end | date: "%-m" %}
            {% if m == n %}
              {{event.date | date: "%B %-d"}}-{{ event.date-end | date: "%-d, %Y"}}
            {% else %}
              {{event.date | date: "%B %-d"}} - {{ event.date-end | date: "%B %-d, %Y"}}
            {% endif %}
          {% else %}
            {{event.date | date: "%B %-d, %Y"}}
          {% endif %}
          </td>
          {% if event.link-url %}
            <td class="align-middle"><a href="{{event.link-url}}" class="btn btn-primary">{{event.link-text}}</a></td>
          {% else %}
            <td class="align-middle">{{event.link-text}}</td>
          {% endif %}
        </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

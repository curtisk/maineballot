---
layout: archive
title: "Local elections"
author_profile: false
permalink: /local/
---

This is a work in progress list of websites or contact information for county, city, and town elections in Maine. The information about what's on the local ballot is based on what we could find on the locality websites, but may not be complete because the websites aren't all up to date with information about the current election. If information about your locality isn't listed and you would like to provide us with the information, please send it to [maineballot@gmail.com](mailto:maineballot@gmail.com).

<input id="town-search" type="text" placeholder="Search for city, town, or county..." />

<table>
    <thead>
        <tr>
        <th>County</th>
        <th>City or town</th>
        <th>Election website</th>
        <th>What's on the ballot</th>
        </tr>
    </thead>
    <tbody>  
    {% for local in site.data.local %}
      <tr data-index="{% county_town_index %}">
        <td>
          {% unless local.city %}
            {{ local.county }}
          {% endunless %}
        </td>
        <td>{{ local.city }}</td>
        <td>
          {% if local.website %}
              <a href="{{ local.website }}">
                {% if local.city %}{{ local.city }}{% else %}{{ local.county }}{% endif %}
                {{ local.type }} website
              </a>
          {% endif %}
        </td>
        <td>{{ local.ballot }}</td>
      </tr>
    {% endfor %}
    </tbody>
</table>
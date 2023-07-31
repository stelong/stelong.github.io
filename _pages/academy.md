---
layout: page
permalink: /academy/
title: My Academic Achievements
---

## Publications

{% for publication in site.data.publications %}
- **{{ publication.title }}**
  <ul class="icon-list">
    <li><span class="icon-small"><img src="{{ "/images/people.png" | relative_url }}" alt="People Icon"></span> {{ publication.authors }}</li>
    <li><span class="icon-small"><img src="{{ "/images/calendar.png" | relative_url }}" alt="Calendar Icon"></span> {{ publication.year }}</li>
    <li><span class="icon-small"><img src="{{ "/images/book.png" | relative_url }}" alt="Book Icon"></span> {{ publication.journal }}</li>
  </ul>
[Link to Publication]({{ publication.link }})
<br>
{% endfor %}

## Oral Presentations

{% for presentation in site.data.presentations %}
- **{{ presentation.title }}**
  <ul class="icon-list">
    <li><span class="icon-small"><img src="{{ "/images/calendar.png" | relative_url }}" alt="People Icon"></span> {{ presentation.date }}</li>
    <li><span class="icon-small"><img src="{{ "/images/location.png" | relative_url }}" alt="Calendar Icon"></span> {{ presentation.location }}</li>
    <li><span class="icon-small"><img src="{{ "/images/conference.png" | relative_url }}" alt="Book Icon"></span> {{ presentation.conference }}</li>
  </ul>
*Contact me for full presentation*
<br>
{% endfor %}

## Posters

{% for poster in site.data.posters %}
- **{{ poster.title }}**
  <ul class="icon-list">
    <li><span class="icon-small"><img src="{{ "/images/calendar.png" | relative_url }}" alt="People Icon"></span> {{ poster.date }}</li>
    <li><span class="icon-small"><img src="{{ "/images/location.png" | relative_url }}" alt="Calendar Icon"></span> {{ poster.location }}</li>
    <li><span class="icon-small"><img src="{{ "/images/conference.png" | relative_url }}" alt="Book Icon"></span> {{ poster.conference }}</li>
  </ul>
{% include download-button.html url=poster.pdf_url text="Download Poster" %}
{% endfor %}

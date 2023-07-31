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
  - *Date*: {{ presentation.date }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }}){:class="icon-small"}
  - *Conference*: {{ presentation.conference }}
  - *Location*: {{ presentation.location }} ![Location Icon]({{ "/images/location.png" | relative_url }}){:class="icon-small"}
{% endfor %}

## Posters

{% for poster in site.data.posters %}
- **{{ poster.title }}**
  - *Date*: {{ poster.date }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }}){:class="icon-small"}
  - *Conference*: {{ poster.conference }}
  - *Location*: {{ poster.location }} ![Location Icon]({{ "/images/location.png" | relative_url }}){:class="icon-small"}
  {% include download-button.html url=poster.pdf_url %}
{% endfor %}

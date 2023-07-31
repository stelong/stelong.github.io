---
layout: page
permalink: /academy/
title: My Academic Achievements
---

## Publications

{% for publication in site.data.publications %}
- **{{ publication.title }}**
  - ![People Icon]({{ "/images/people.png" | relative_url }}){:class="icon-small"} {{ publication.authors }}
  - ![Calendar Icon]({{ "/images/calendar.png" | relative_url }}){:class="icon-small"} {{ publication.year }}
  - ![Book Icon]({{ "/images/book.png" | relative_url }}){:class="icon-small"} {{ publication.journal }}
[Link to Publication]({{ publication.link }})
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

---
layout: page
permalink: /academy/
title: My Academic Achievements
---

## Publications

{% for publication in publications %}
- **{{ publication.title }}**
  - *Authors*: {{ publication.authors }} ![People Icon]({{ "/images/people.png" | relative_url }})
  - *Year*: {{ publication.year }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }})
  - *Journal*: [{{ publication.journal }}]({{ publication.link }}) ![Book Icon]({{ "/images/book.png" | relative_url }})
{% endfor %}

## Oral Presentations

{% for presentation in site.data.oral_presentations %}
- **{{ presentation.title }}**
  - *Date*: {{ presentation.date }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }})
  - *Conference*: {{ presentation.conference }}
  - *Location*: {{ presentation.location }} ![Location Icon]({{ "/images/location.png" | relative_url }})
{% endfor %}

## Posters

{% for poster in site.data.posters %}
- **{{ poster.title }}**
  - *Date*: {{ poster.date }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }})
  - *Conference*: {{ poster.conference }}
  - *Location*: {{ poster.location }} ![Location Icon]({{ "/images/location.png" | relative_url }})
  {% include download-button.html url=poster.pdf_url %}
{% endfor %}

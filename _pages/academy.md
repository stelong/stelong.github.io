---
layout: page
permalink: /academy/
title: My Academic Achievements
---

## Publications

{% assign publications = site.data.publications %}

{% for publication in publications %}
- **{{ publication.title }}**
  - *Authors*: {{ publication.authors }} ![People Icon]({{ "/images/people.png" | relative_url }})
  - *Year*: {{ publication.year }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }})
  - *Journal*: [{{ publication.journal }}]({{ publication.link }}) ![Book Icon]({{ "/images/book.png" | relative_url }})
{% endfor %}

## Oral Presentations

{% for presentation in site.data.presentations %}
- **{{ presentation.title }}**
  - ![Calendar Icon]({{ "/images/calendar.png" | relative_url }}) {{ presentation.date }}
  - ![Location Icon]({{ "/images/location.png" | relative_url }}) {{ presentation.location }}
  - *Conference*: {{ presentation.conference }}
{% endfor %}

## Posters

{% for poster in site.data.posters %}
- **{{ poster.title }}**
  - ![Calendar Icon]({{ "/images/calendar.png" | relative_url }}) {{ poster.date }}
  - ![Location Icon]({{ "/images/location.png" | relative_url }}) {{ presentation.location }}
  - *Conference*: {{ poster.conference }}
  {% include download-button.html file=page.path url=poster.pdf_url %}
{% endfor %}

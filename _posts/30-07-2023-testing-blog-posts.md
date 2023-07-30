---
layout: post
title: "My Academic Achievements"
categories: Miscellaneous
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

{% for presentation in site.data.oral_presentations %}
- **{{ presentation.title }}**
  - *Date*: {{ presentation.date }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }})
  - *Conference*: {{ presentation.conference }}, {{ presentation.location }}
  {% include download-button.html file=page.path url=presentation.pdf_url %}
{% endfor %}

## Posters

{% for poster in site.data.posters %}
- **{{ poster.title }}**
  - *Date*: {{ poster.date }} ![Calendar Icon]({{ "/images/calendar.png" | relative_url }})
  - *Conference*: {{ poster.conference }}, {{ poster.location }}
  {% include download-button.html file=page.path url=poster.pdf_url %}
{% endfor %}

---
layout: null
permalink: /generate_search_index.json
---

[
  {% for page in site.pages %}
    {% if page.path contains '_pages/' %}
      {
        "title": "{{ page.title | escape }}",
        "content": "{{ page.content | strip_html | strip_newlines | escape }}"
      }{% unless forloop.last %},{% endunless %}
    {% endif %}
  {% endfor %}
]

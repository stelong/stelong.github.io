---
layout: page
permalink: /publications/
---

Here you can find all my publications, as well as talks and posters I have presented at conferences. If you're curious to know more about a specific research topic, don't hesitate to reach out!

## Publications

### First Author

{% for publication in site.data.publications_first %}
- **{{ publication.title }}**
  <ul class="icon-list">
    <li><span class="icon-small"><img src="{{ "/images/people.png" | relative_url }}" alt="People Icon"></span> {{ publication.authors }}</li>
    <li><span class="icon-small"><img src="{{ "/images/calendar.png" | relative_url }}" alt="Calendar Icon"></span> {{ publication.year }}</li>
    <li><span class="icon-small"><img src="{{ "/images/book.png" | relative_url }}" alt="Book Icon"></span> {{ publication.journal }}</li>
  </ul>
[{{ publication.link }}]({{ publication.link }})
<br>
{% endfor %}

### Others

{% for publication in site.data.publications_others %}
- **{{ publication.title }}**
  <ul class="icon-list">
    <li><span class="icon-small"><img src="{{ "/images/people.png" | relative_url }}" alt="People Icon"></span> {{ publication.authors }}</li>
    <li><span class="icon-small"><img src="{{ "/images/calendar.png" | relative_url }}" alt="Calendar Icon"></span> {{ publication.year }}</li>
    <li><span class="icon-small"><img src="{{ "/images/book.png" | relative_url }}" alt="Book Icon"></span> {{ publication.journal }}</li>
  </ul>
[{{ publication.link }}]({{ publication.link }})
<br>
{% endfor %}

<div class="custom-ruler"></div>
## Talks

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

<div class="custom-ruler"></div>
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

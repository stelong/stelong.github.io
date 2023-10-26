---
layout: page
permalink: /search/
title: Search
---

Not a massive list of projects posted on this website to justify a searchbar functionality. Yet, if you are feeling lazy, you can type e.g., 'python' to see If I've used Python in any of the projects.

<div id="search-container">
    <input type="text" id="search-input" placeholder="Search through the projects...">
    <ul id="results-container"></ul>
</div>

<script src="{{ site.baseurl }}/assets/simple-jekyll-search.min.js" type="text/javascript"></script>

<script>
    SimpleJekyllSearch({
        searchInput: document.getElementById('search-input'),
        resultsContainer: document.getElementById('results-container'),
        searchResultTemplate: '<div style="text-align: left !important;"><a href="{url}"><h1 style="text-align:left !important;">{title}</h1></a><span style="text-align:left !important;"> {category}</span></div>',
        json: '{{ site.baseurl }}/search.json'
    });
</script>

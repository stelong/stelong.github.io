---
layout: page
permalink: /search/
title: Search
---

Type 'python' for example to see in which projects I've used Python.

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

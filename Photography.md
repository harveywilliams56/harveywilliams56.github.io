---
layout: page
title: "Photography"
order: 1000
permalink: /photography
---

<div>

{% for image in site.static_files %}
    {% if image.path contains 'images/portfolio' %}
	<a href="{{ site.baseurl }}{{ image.path }}">
        <img src="{{ site.baseurl }}{{ image.path }}" alt="image" style="width:180px; padding:5px; border-radius:20px"/>
	</a>
    {% endif %}
{% endfor %}
</div>
